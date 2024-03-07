---
description: >-
  Con nuestro middleware controlamos los loggs y tambien toda la validacion en
  cuanto a los dtos, cors, con esto validamos la lista de urls que pueden
  consultar nuestros servicios
---

# Middleware

Desntro de `/middlware`

{% code title="cors.validate.ts" overflow="wrap" lineNumbers="true" %}
```javascript
import { CorsOptions } from "cors";

const whiteList = ["http://localhost:3000", "http://localhost:4000"];
export const options: CorsOptions = {
  origin: (origin, callback) => {
    if (!origin || whiteList.indexOf(origin) !== -1) {
      callback(null, true);
    } else {
      callback(new Error("access denied - CORS-disabled to white list"));
    }
  },
  methods: ["GET", "POST", "DELETE", "UPDATE", "PUT", "PATCH"],
};

```
{% endcode %}

aqui los loggs que me van a dar mayor visibilidad al momento de trackear errores&#x20;

{% code title="errors.handler.ts" overflow="wrap" lineNumbers="true" %}
```javascript
import { ErrorRequestHandler } from "express";
export const logErrors: ErrorRequestHandler = (error, req, res, next) => {
  console.error(error);
  next(error);
};

export const handleErrors: ErrorRequestHandler = (error, req, res, next) => {
  res.status(500).json({
    message: error.message,
    stack: error.stack,
  });
};

export const boomHandleErrors: ErrorRequestHandler = (
  error,
  req,
  res,
  next
) => {
  if (error.isBoom) {
    const { payload, statusCode } = error.output;
    res.status(statusCode).json({
      payload,
    });
  } else {
    next(error);
  }
};

export const ormHandlerError: ErrorRequestHandler = (error, req, res, next) => {
  if (error?.sql) {
    res.status(409).json({
      statusCode: 409,
      message: error.errors.name,
      errors: error.errors,
    });
  }
  next(error);
};

```
{% endcode %}

Y aqui el archivo middleware que encapsula todas las validaciones

{% code title="middleware.ts" overflow="wrap" lineNumbers="true" %}
```javascript
import boom from "@hapi/boom";
import { NextFunction, Request, Response } from "express";
import Joi from "joi";

export const validateHandler = (
  dto: Joi.ObjectSchema<any>,
  property: string
) => {
  return (req: any, res: Response, next: NextFunction) => {
    const data = req[property];
    const { error } = dto.validate(data, { abortEarly: false });
    if (error) next(boom.badRequest(error));
    next();
  };
};

```
{% endcode %}
