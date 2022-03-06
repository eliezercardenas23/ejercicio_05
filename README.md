# Author
Eliézer Cárdenas


***************************************************
Healthcheck
****************************************************

Un Healthcheck es un comando que permite comprobar el estado de un contenedor, exponiendo la disponibilidad de su carga de trabajo lo cual es diferente a solo comprobar si el contenedor se está ejecutando.

Si por ejemplo la BD deja de funcionar esto traerá como consecuencia que el API no pueda realizar consultas, si ejecutamos un simple docker ps informaría que el contenedor está disponible, pero agregar un Healthcheck amplía la salida de docker ps para incluir el estado real del contenedor.

Los códigos de salida de Healthcheck son:

0: el contenedor está sano y funciona normalmente.
1: El contenedor no es saludable; es posible que la carga de trabajo no esté funcionando.
2: este código de estado está reservado por Docker y no debe usarse.


***************************************************
OnBuild
****************************************************

El comando ONBUILD se usa para especificar los comandos que se ejecutan después que se completa la compilación actual de un Dockerfile. Es útil para imágenes que se van a construir a partir de una imagen base.

Podemos usar esta instrucción ONBUILD donde necesita una imagen base estática con un valor de configuración dinámica que cambia en una nueva imagen o podemos usarla en una situación en la que una nueva imagen depende de la imagen anterior.

NOTA: Las imágenes creadas a partir de ONBUILD deben tener una etiqueta independiente, por ejemplo: ruby:1.9-onbuild o ruby:2.0-onbuild.


***************************************************
Volume
****************************************************

De forma predeterminada, los contenedores de Docker son volátiles y los datos almacenados en el contenedor se borrarán cuando el contenedor se apague. Obviamente, esto no es ideal para muchas aplicaciones, por lo que Docker proporciona los volúmenes para resolver esto.

Los volúmenes son como discos duros virtuales administrados por Docker para conservar los datos generados por el contenedor en ejecución. Docker se encarga de almacenarlos en el disco (generalmente en /var/lib/docker/volumes/) y les otorga un nombre único fácil de recordar en lugar de una ruta de directorio. Es fácil crearlos y eliminarlos usando la CLI de Docker.

Es importante considerar si realmente necesita que los datos de Docker se almacenen en el servidor. Para muchas aplicaciones, usar un almacén de datos remoto externo como Amazon S3 o una base de datos externa es suficiente para almacenar los datos que usan sin atarlos al servidor docker.


