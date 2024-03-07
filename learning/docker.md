---
cover: https://www.zadara.com/wp-content/uploads/docker.png
coverY: 107
---

# 🐳 Docker

{% hint style="warning" %}
**Crear un archivo:** Debemos crear un archivo docker-compose.yml
{% endhint %}

```yaml
// Some code
version: '3.3'

services:
    postgres:
        image: postgres:13
        environment:
          - POSTGRES_DB=my_store
          - POSTGRES_USER=gelvezz23
          - POSTGRES_PASSWORD=carlos123
        ports:
          - 5432:5432
```

## Comandos

### levantar el servicio

```
docker compose up -d postgres
```

**up** : para levantar docker

**-d** : correr en segundo plano&#x20;

**postgres**: nombre de nuestro servicio en el archivo .yml

### ver los servicios corriendo

```
docker compose ps
```

**ps** : ver los procesos que estan corriendo en segundo plano

### bajar los servicios corriendo

```
docker compose down
```

down : bajar los servicios que estan corriendo&#x20;

### crear volumenes para persistir estados de informacion

```yaml
version: '3.3'

services:
    postgres:
        image: postgres:13
        environment:
          - POSTGRES_DB=my_store
          - POSTGRES_USER=gelvezz23
          - POSTGRES_PASSWORD=carlos123
        ports:
          - 5432:5432
        volumes:
          - ./postgres_data:/var/lib/postgres/dataym
```

creamos la linea de volumenes en el `archivo .yml` y creamos una carpeta llamada `postgres_data`

### explorar el servicio corrido en Docker

```
docker compose exec postgres bash
```

conectar se desde la terminal&#x20;

### entrar a la base de datos de Postgres

```
psql -h localhost -d my_store -U gelvezz23
```

**my\_store**: es el nombre que le colocamos en el archivo `.yml POSTGRES_DB=my_store`

**gelvezz23**: es el usuario que lo colocamos en el archivo `.yml` `POSTGRES_USER=gelvezz23`

### salir de la BD

```
\q
```

### salir del contenedor

```
exit
```

