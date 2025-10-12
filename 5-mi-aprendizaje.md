# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

Antes no sabía cómo conectar contenedores entre sí ni cómo funcionaban las redes en Docker, ahora aprendí a crear contenedores que se comunican, usar variables de entorno y montar servicios completos como WordPress con MySQL.

Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).

## Docker Secrets

Docker Secrets permite manejar datos confidenciales (como contraseñas, tokens o claves) de forma segura y cifrada.  
Los secretos no se almacenan en texto plano ni en variables de entorno, sino que se montan como archivos temporales dentro del contenedor.

```
# Crear un secreto
echo "claveSegura123" | docker secret create db_password -

# Iniciar el modo swarm
docker swarm init

# Crear un servicio que use el secreto
docker service create --name mysqlSrv --secret db_password \
  -e MYSQL_ROOT_PASSWORD_FILE="/run/secrets/db_password" mysql:8

# Listar secretos
docker secret ls

# Eliminar secreto
docker secret rm db_password

```
Los secretos solo están disponibles para los servicios que los solicitan y desaparecen al eliminar el contenedor o el servicio, garantizando la confidencialidad de los datos
