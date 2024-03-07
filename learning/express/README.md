---
description: Estoy aprendiendo Node con Express - aqui mis apuntes
cover: >-
  https://images.unsplash.com/photo-1633356122102-3fe601e05bd2?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxleHByZXNzJTIwanN8ZW58MHx8fHwxNjg3MzY0NDUzfDA&ixlib=rb-4.0.3&q=85
coverY: 0
---

# 👾 Express

{% hint style="info" %}
**Tener en cuenta:** Las versiones que estoy usuando de Node son:&#x20;

* nvm 0.39.1
* node 18.7.0
* npm 8.15.0
{% endhint %}

## Paso 1 - Configuracion de Entorno&#x20;

Empece por tener `VS Code instalado`&#x20;

Ya teniendo todo esto claro vamos a ir a la consola, parado en tu proyecto y escribir lo siguiente.

```
npm init \
```

```

package name: (backendnode)
version: (1.0.0)
description:
entry point: (index.js)
test command:
git repository:
keywords:
author: Carlos Mario Gomez Gelvez
license: (ISC)
About to write to /Users/carlos.gomez/Documents/backendnode/package.json:

{
  "name": "backendnode",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Carlos Mario Gomez Gelvez",
  "license": "ISC"
}


Is this OK? (yes)
```

Al darle `Yes` ya nos va a crear un `package.json`

con la informacion&#x20;

```json
{
  "name": "backendnode",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Carlos Mario Gomez Gelvez",
  "license": "ISC"
}
```

