# Informacion basica para uso de Docker

## Conceptos basicos

- ¿Que es una imagen? Una imagen basicamente es una copia de "la maquina virtual", con ciertas configuraciones que tendra el contenedor para poder correr el programa

## Notas Ssoft

- aparentementa hay que estar registrado para poder usar las imagenes

## Comandos

- `docker pull numbre_imagen` con este comando podremos descargar imagenes

- `docker images` Con este comando podemos ver las imagenes    que hay actualmente en el computador instaladas

-  `docker run nombre_imagen` Este comando nos sirve para correr una imagen
   - Modo de uso: se ponen comandos directamente al correr una imagen. Ejemplo: `docker run nombre_imagen ls` con este ejemplo correra la imagen y mostrara un listado de las carpetas que hay dentro de ese contenedor. Tambien hay que tener en cuenta que justo de que termine de hacer lo que le indiquemos el contenedor cerrara
- `docker run -it nombre_imagen` con este comando correremos el contenedor solo que este no se cerrara hasta que se lo indiquemos
- `exit` como su nombre lo dice con este comando salimos de el contenedor
- `docker ps` con este comando podemos hacer un tracking de que estan haciendo los contenedores actualmente
  - `docker ps -a` con esto podemos ver el historial de lo que han hecho los contenedores
- `docker run -rm nombre_imagen` con esto eliminaremos el contenedor luego de haberlo utilizado

###  NOTA
Docker por defecto no guarda los archivos que uno genere al uno utilizar un contenedor Luego de que este se cierre los archivos se eliminaran

- `docker run -v` con este comando hacemos que los archivos que generemos en el contenedor se nos guarde en nuestra maquina
  - por lo que veo lo ideal es que lo utilize de esta forma `docker run -v ${PWD}:/usr/src/app`
