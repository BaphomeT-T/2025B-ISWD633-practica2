## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# COMPLETAR
docker network create net-wp

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# COMPLETAR
docker run -d --name mysqlSrv --network net-wp -e MYSQL_ROOT_PASSWORD=admin -e MYSQL_DATABASE=wpdb -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin mysql:8

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR
docker run -d --name wordpressSrv --network net-wp -p 3000:80 -e WORDPRESS_DB_HOST=mysqlSrv:3306 -e WORDPRESS_DB_USER=admin -e WORDPRESS_DB_PASSWORD=admin -e WORDPRESS_DB_NAME=wpdb wordpress

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **(3000)**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN
<img width="935" height="850" alt="image" src="https://github.com/user-attachments/assets/b68c94db-25e5-4729-8d4f-aef988e1c719" />

Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
<img width="1901" height="1016" alt="image" src="https://github.com/user-attachments/assets/efe8e7fd-0de8-487c-b677-d4d349eac8ee" />

### Eliminar el contenedor wordpress
# COMPLETAR
docker rm -f wordpressSrv

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR
<img width="1859" height="847" alt="image" src="https://github.com/user-attachments/assets/7ced4e32-1c1e-4cd7-b2c6-3041478165f8" />
la publicacion sigue ahí, la imagen que tenía no, ademas el tema no está aplicado.

