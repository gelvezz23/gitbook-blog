---
description: >-
  Aqui vamos a instalar todo lo necesario para correr typescript y tener un
  servidor corriendo de Express js
---

# Configuration

Voy a darte como tengo mi `package.json` de esta forma solo tienes que copiar y pegar y luego correr el comando `npm install`&#x20;

{% code title="" overflow="wrap" lineNumbers="true" %}
```json
{
  "name": "my-store",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build": "npx tsc",
    "start": "node dist/index.js",
    "dev": "nodemon",
    "migration:generate": "sequelize-cli migration:generate --name",
    "migration:run": "sequelize-cli db:migrate",
    "migration:revert": "sequelize-cli db:migrate:undo",
    "migration:delete": "sequelize-cli db:migrate:undo:all"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@types/cors": "2.8.13",
    "@types/express": "^4.17.17",
    "@types/faker": "^6.6.9",
    "@types/node": "18.14.6",
    "@types/pg": "8.6.6",
    "concurrently": "7.6.0",
    "eslint": "^7.32.0",
    "eslint-config-prettier": "^8.3.0",
    "eslint-plugin-prettier": "^3.4.1",
    "nodemon": "2.0.21",
    "prettier": "^2.3.2",
    "sequelize-cli": "6.6.0",
    "ts-node": "10.9.1",
    "typescript": "4.9.5"
  },
  "dependencies": {
    "@hapi/boom": "10.0.1",
    "cors": "2.8.5",
    "dotenv": "16.0.3",
    "express": "4.18.2",
    "faker": "^5.5.3",
    "helmet": "6.0.1",
    "joi": "17.8.4",
    "mysql2": "3.2.0",
    "pg": "8.10.0",
    "pg-hstore": "2.3.4",
    "sequelize": "6.30.0",
    "sqlite3": "5.1.6"
  }
}

```
{% endcode %}

el archivo `tsconfig.json`

{% code title="" overflow="wrap" lineNumbers="true" %}
```json
{
  "include": ["**/*", ".sequelizerc"],
    "compilerOptions": {
      "target": "es2016",
      "module": "commonjs",
      "moduleResolution": "node",
      "sourceMap": true,
       "outDir": "./dist",
      "esModuleInterop": true,
      "forceConsistentCasingInFileNames": true,
      "strict": true,
      "skipLibCheck": true
    }
  }
```
{% endcode %}

archivo `nodemon.json`

{% code title="" overflow="wrap" lineNumbers="true" %}
```json
{
  "watch": ["app", "middlewares", "config", "libs", "db"],
  "ext": "ts",
  "exec": "ts-node app/index.ts"
}

```
{% endcode %}

archivo `eslintrc.json`

{% code title="" overflow="wrap" lineNumbers="true" %}
```json
{
  "parserOptions": {
    "ecmaVersion": 2018
  },
  "extends": ["eslint:recommended", "prettier"],
  "env": {
    "es6": true,
    "node": true,
    "jest": true
  },
  "rules": {
    "no-console": "warn"
  }
}

```
{% endcode %}

Las carpetas que eh usado son&#x20;

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-04-17 a la(s) 1.17.27 p.m..png" alt=""><figcaption><p>estructura de carpetas</p></figcaption></figure>

