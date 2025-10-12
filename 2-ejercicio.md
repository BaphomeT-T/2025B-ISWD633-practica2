### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21
# COMPLETAR
docker run -d --name postgresSrv -e POSTGRES_PASSWORD=admin postgres:15-alpine3.21

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4

# COMPLETAR
docker run -d --name pgAdminSrv -e PGADMIN_DEFAULT_EMAIL=admin@mail.com -e PGADMIN_DEFAULT_PASSWORD=admin -p 8080:80 dpage/pgadmin4

La figura presenta el esquema creado en donde los puertos son:
- a: (8080)
- b: (80)
- c: (5432)

![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
# COMPLETAR CON UNA CAPTURA DEL LOGIN
<img width="652" height="552" alt="image" src="https://github.com/user-attachments/assets/96970d84-3076-4c2f-9479-0e7806f94a9b" />

Importante para crear servidores:

docker network create postgresNet

docker network connect postgresNet postgresSrv

docker network connect postgresNet pgAdminSrv

### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.

## Desde el servidor postgresl
### Acceder al servidor
### Conectarse a la base de datos info
# COMPLETAR
docker exec -it postgresSrv psql -U postgres

postgres=# \c info
### Realizar un select *from personas
# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO
<img width="588" height="196" alt="image" src="https://github.com/user-attachments/assets/c15abc7a-22f6-4036-be70-a9bc928c7182" />
