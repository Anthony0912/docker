# Imagenes - Docker

- Por medio de Tag
```bash
docker pull mongo:3.6.5-jessie
```

- Muestra lista de imágenes
```bash
docker image for mongo:latest
docker images | grep mysql
```

- Crear mi propia imagen
```bash
mkdir docker-images
nano (code, vi, subl) Dockerfile
docker build --tag apache-centos . | docker build --tag apache-centos:latest .
docker history -H apache-centos:latest
```

- Crear contenedor y agregar la imagen al contenedor.

Borrar contenedor
```bash
docker ps -a
sudo docker rm -fv quizzical_easley
```

Crear contenedor
```bash
docker run -d apache-centos
docker run -d --name container-apache apache-centos
docker run -d --name container-apache apache-centos:apache-cmd
```

Habilitrar puerto via web en el contenedor
```bash
docker run -d --name container-apache -p 80:80 apache-centos:apache-cmd
```

Ver salidas completas
```bash
docker ps --no-trunc
```

Ver logs de la imagen
```bash
docker logs -f container-apache
```

[Volver al menu](./README.md)