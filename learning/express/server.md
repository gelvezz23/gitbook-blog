---
description: >-
  Aqui vamos a ver como crear el server, montarlo y correr lo, recuerda que a
  estoy mostrando te mi codigo como yo lo hice pero esto no quiere decir que
  pueda ser mejor
---

# Server

La carpeta `/App/index.ts`

{% code title="index.ts" overflow="wrap" lineNumbers="true" %}
```javascript
import dotenv from "dotenv";
import { Server } from "./server";

dotenv.config();
Server();
```
{% endcode %}

Y en `server/index.ts`

{% code title="index.ts" overflow="wrap" lineNumbers="true" %}
```javascript
export * from "./server";
```
{% endcode %}

{% code title="server.ts" overflow="wrap" lineNumbers="true" %}
```javascript
import express, { Application } from "express";
import helmet from "helmet";
import cors from "cors";
import {
  handleErrors,
  logErrors,
  boomHandleErrors,
  ormHandlerError,
} from "../../middleware/errors.handler";
import { router } from "./router";
import { options } from "../../middleware/cors.validate";
import { sequelize_postgres } from "../../libs/sequelize/sequelize_postgres";

export const Server = () => {
  const app: Application = express();
  const port: string = process.env.PORT || "";
  const host: string = process.env.URL || "";
  app.use(express.json());
  app.use(helmet());
  app.use(cors(options));

  const listen = () => {
    try {
      sequelize_postgres.authenticate();
      router(app);
      app.use(logErrors);
      app.use(ormHandlerError);
      app.use(boomHandleErrors);
      app.use(handleErrors);
      app.listen(port, () => {
        console.log(`CORS-enabled web server listening on port ${port}`);
        console.log(`Run app in ${host}:${port}`);
      });
    } catch (error) {
      console.log("Error:", error);
    }
  };

  listen();
};

```
{% endcode %}

Antes de pasar a ver los loggs tenemos que ver como manejamos las rutas (`router.ts`)

{% code title="router.ts" overflow="wrap" lineNumbers="true" %}
```javascript
import { Application } from "express";
import { Path as path } from "./paths";

import productsRouter from "../products/products.router";
import categoriesRouter from "../categories/categories.router";
import customerRouter from "../customer/customer.router";
import usersRouter from "../users/user.router";
import orderRouter from "../orders/order.router";
import orderProductRouter from "../order-products/order-product.router";

export const router = (app: Application) => {
  app.use(path.products, productsRouter);
  app.use(path.categories, categoriesRouter);
  app.use(path.users, usersRouter);
  app.use(path.customer, customerRouter);
  app.use(path.order, orderRouter);
  app.use(path.orderProduct, orderProductRouter);
};

```
{% endcode %}

{% code title="path.ts" overflow="wrap" lineNumbers="true" %}
```javascript
import { PathProps } from "./types";

export const Path: PathProps = {
  products: "/api/products",
  categories: "/api/categories",
  users: "/api/users",
  customer: "/api/customer",
  order: "/api/order",
  orderProduct: "/api/orderProduct",
  auth: "api/auth",
};

```
{% endcode %}

{% code title="types.ts" overflow="wrap" lineNumbers="true" %}
```javascript
export interface PathProps {
  products: string;
  categories: string;
  users: string;
  customer: string;
  order: string;
  orderProduct: string;
  auth: string;
}
```
{% endcode %}

Ya con eso tenemos montado nuestro Server, ahora debemos de ir a crear los `servicios`, `controladores`, `routers`, `modelos` y `dtos`&#x20;

