# 🐳 Pgadmin - Docker

### crear nuevo servicio

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
          - ./postgres_data:/var/lib/postgresql/data
    
    pgadmin:
      image: dpage/pgadmin4
      environment:
          - PGADMIN_DEFAULT_EMAIL=mao_23_@hotmail.com
          - PGADMIN_DEFAULT_PASSWORD=carlos123
      ports:
        - 5050:80
```

creamos el servicio de pgadmin y lo corremos `docker compose up -d pgadmin`

### ver informacion del servicio corriendo

por interface grafica lo puedes ver [`ttp://localhost:5050`](http://localhost:5050)

<div align="center">

<figure><img src="../.gitbook/assets/Captura de pantalla 2023-03-17 a la(s) 9.43.21 a.m..png" alt=""><figcaption></figcaption></figure>

</div>

Vamos a darle en `Add new server`

<figure><img src="../.gitbook/assets/Captura de pantalla 2023-03-17 a la(s) 10.14.25 a.m..png" alt=""><figcaption></figcaption></figure>

Esto nos va a pedir una informacion que la sacaremos de la siguiente form

```
docker ps
```

nos dara el ID de el contenedor (el que sea de postgres)

```
docker inspect c43a2a79ba50
```

Ahi vamos a meter la `IPAddress` en la parte de connection y que los datos concuerden con nuestro archivo `.yml`
