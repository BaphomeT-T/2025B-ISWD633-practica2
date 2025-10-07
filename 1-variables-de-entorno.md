# Variables de Entorno
### ¿Qué son las variables de entorno?
# COMPLETAR
Valores dinámicas que residen en el sistema operativo, tienen nombre y valor y sirven para proporcionar información a programas sobre el sistema o la sesión actual.
### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# COMPLETAR
docker run -d --name ngEnt -e username=Paul -e role=admin nginx:alpine

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
Usando: docker inspect ngEnt
<img width="862" height="248" alt="image" src="https://github.com/user-attachments/assets/0bae7c4e-e959-452d-9c39-fd30db0c3555" />

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# COMPLETAR
docker run -d --name mysqlsrv -P mysql
### ¿El contenedor se está ejecutando?
# COMPLETAR
No se está ejecutando.
### Identificar el problema
# COMPLETAR
2025-10-07 20:20:14+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 9.4.0-1.el9 started.
2025-10-07 20:20:14+00:00 [Note] [Entrypoint]: Switching to dedicated user 'mysql'
2025-10-07 20:20:14+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 9.4.0-1.el9 started.
2025-10-07 20:20:15+00:00 [ERROR] [Entrypoint]: Database is uninitialized and password option is not specified
    You need to specify one of the following as an environment variable:
    - MYSQL_ROOT_PASSWORD
    - MYSQL_ALLOW_EMPTY_PASSWORD
    - MYSQL_RANDOM_ROOT_PASSWORD
    
### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### Crear un contenedor con mysql, mapear todos los puertos y configurar las variables de entorno mediante un archivo
# COMPLETAR
P3E010-D>docker run -d --name mysqlsrv -P -e MYSQL_ROOT_PASSWORD=admin mysql
# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 

### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR
<img width="307" height="268" alt="image" src="https://github.com/user-attachments/assets/80270545-5c20-4433-b658-a1de66cf08e1" />
