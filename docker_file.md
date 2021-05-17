# Doker File
Definicion de la configuracion de la imagen
- FROM: Definimos que sistema operativo queremos en nuestra imagen o especificamos una imagen creada por nosotros mismos

- RUN: Son instrucciones que se pueden crear en la terminal
- COPY/ADD: Copiar archivos de nuestra maquina hacia la imagen
- ENV: Variables de entorno
- WORKDIR: Directorios de trabajo
- EXPOSE: Exponer los puertos
- LABEL:
- USER: Que usuario va a ejecutar la tarea
- VOLUME: data que se encuentra dentro del contenedor se guarde en nuestra maquina
- CMD: Es el proceso que mantiene vivo el contenedor se ejecuta en primer plano
- .dockerignore: Ignora los archivos que no queremos subir

## COPY

```bash
COPY portafolio /var/www/html
```

## ADD

```bash
ADD portafolio /var/www/html
```

## ENV

```bash
ENV contenido prueba
RUN echo "$contenido" > /var/www/html/prueba.html
```

## WORKDIR

```bash
WORKDIR /var/www/html
COPY portafolio .
```

## EXPOSE

```bash
EXPOSE 8080
```

## LABEL

```bash
LABEL version=1.0
LABEL description="This is an apache image"
```

## USER
```bash
RUN echo "$(whoami)" > /var/www/html/user1.html

RUN useradd ricardo

RUN chown ricardo /var/www/html -R

USER ricardo

RUN echo "$(whoami)" > /tmp/user2.html

USER root

RUN cp /tmp/user2.html /var/www/html/user2.html
``` 

## VOLUMEN

```bash
VOLUMEN /var/www/html
```

## CMD

```bash
COPY run.sh /run.sh

CMD sh /run.sh
```

[Volver al menu](./README.md)