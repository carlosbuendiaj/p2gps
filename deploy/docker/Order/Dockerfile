FROM openjdk:8-jre

MAINTAINER cralos1998@hotmail.com

RUN mkdir -p /usr/local/app

#WORKDIR /usr/local/app

#copiar el .jar del servicio a la imagen
#No se indica el nombre porque las versiones pueden cambiar
COPY drop/*.jar usr/local/app

#copiar script que se ejecutara al lanzar el contenedor
COPY drop/run.sh usr/local/app/run.sh

#Si ejecutaramos la imagen en local, este servicio tendria acceso
#local a la ip del host de Mongo. Pero como lanzaremos como una pila
#de servicios Docker (parecido a produccion con una red privada),
#la ip de MongoDB no se puede descubrir al menos que se la pasemos
#en un archivo de propiedades
COPY drop/application.properties.txt application.properties

EXPOSE 8080

ENTRYPOINT sh run.sh
