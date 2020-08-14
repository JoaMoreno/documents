# Comandos

Lista de comandos que se suelen utilizar.

## Windows

#### Lista procesos con sus puertos y ID.

> netstat –ano

#### Lista conexiones activas
> netstat -a

## Docker

#### Ejecutar consola en docker container con privilegios
(-t) indicamos a docker que deje un terminal abierto 
(-t) para trabajar de forma interactiva (-i) con el contenedor

> docker exec -u root -t -i container_id /bin/bash
> docker exec -u 0 -it container_id /bin/bash

#### Definir el puerto del docker que va a usar la pc
En este caso el puerto 3000 será el 80 del docker
(-d) ejecutarlo de forma desacoplado, sin tener que dejar la consola encendida.

> docker run -p 3000:80 -d image_name

#### Procesos ejecutándose
> docker ps

#### Detener un proceso (pueden ser los primeros 3 dígitos del container id)
> docker stop 123

#### Eliminar todos los contenedores
> docker rm $(docker ps -aq)
>
#### Utilizar un volumen
> docker run -p 3000:80 -d -v $(pwd)/path/file:/docker/path/ image_name
> ej: docker run -p 3000:80 -d -v $(pwd)/src:/var/www/html practice-php
>
#### Guardar los cambios
> docker -t tag-name:version-1.0 .