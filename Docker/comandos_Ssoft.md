# Ejemplo basico para crear una app de Rails con Docker

- `docker run -it -rm -v ${PWD}:/usr/src/app ruby:3.1 bash`
  - con este comando lo que hacemos es crear un nuevo contenedor que este se nos quede abierto hasta que lo cerremos manualmente, que nos guarde los archivos que creemos y por algun motivo que este contenedor se elimine luego de que lo cerremos ademas este contenedor es con la imagen ruby y su version es la 3.1 ademas el contenedor abrira la terminal al (Esto se hace con `bash`)

## Luego de aqui ya van comandos basicos para crear una app de rails

- `gem install rails`
  - este comando instalara la gema rails en nuestro contenedor
- `rails new nombre_proyecto`
  - con este comando creamos una app de rails

## NOTA IMPORTANTE

se debe crear un archivo llamado `dockerfile` y la estructura va algo asi:

```
# Aqui va la imagen que queremos utilizar
FROM ruby:3.1

# Aqui van los comandos que queremos que corran
RUN apt-get update -yqq
RUN apt-get upgrade --yqq
# Aqui faltaria lo de NodeJS

# Esto significaria que va a copiar los archivos de la carpeta y los pegara en la ruta de este contenedor
COPY . /usr/src/app/

# Esto significa que todos lo comandos que se hagan se hacen en la ruta anteriormente especificada
WORKDIR /usr/src/app/

# Queremos que haga un bundle install para instalar las gemas del proyecto
RUN bundle install

```

- Luego se debe hacer el comando `docker build` para que este construya el contenedor en base a el archivo dockerfile que esta en esa carpeta
- debo hacer `docker images` para listar los contenedores ya que luego necesito el id de los contenedores
- Para correr el contenedor y levantar el servidor debo hacer `docker run -p 3001:3000 identificador_del_contenedor rails s -b 0.0.0.0` y de esta forma podremos entrar entrar a el localhost desde nuestra maquina pero realmente la app esta en un contenedor
- para ponerle un nombre a el contenedor hacemos `docker tag identificador nombre_que_le_queramos_poner`
