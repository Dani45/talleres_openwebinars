# Docker, kubernetes y OpenShift

## Objetivos

* Presentar las nuevas metodologías de implantación de aplicaciones web 
* Repasar los conceptos sobre contenedores
* Introducir el trabajo con contenedores con docker
* Estudiar el ciclo de vida de las aplicaciones implantadas en contenedores docker
* Introducir el concepto de orquestador de contenedores
* Repasar los conceptos sobre kubernetes
* Probar el funcionamiento del cluster kubernetes
* Introducir el concepto de PaaS
* Desplegar una aplicación web en OpenShift

## Nivel

Intermedio

## ¿Qué aprenderás en el taller?

* Repasar conceptos sobre docker, kubernetes u openshift
* Desplegar una apalicación en un contendor docker
* Desplegar una aplicación en un cluster kubernetes
* Desplegar una aplicación en openshift

## Conocimientos previos

* Conocer los conceptos básicos de alguna tecnología de contenedores (por ejemplo docker)
* Conocer los recursos que nos ofrece un cluster de kubernetes
* Conocimientos básicos sobre Cloud Computing PaaS

## Desarrollo

### Docker

1. Creamos varios contenedores:
        
        docker run --name servidorweb -d -p 80:80 nginx

        docker run --name servidorweb2 -d -p 8080:80 apache2

    Probamos diferenciones opciones: 

        docker ps
        docker image ls
        docker logs ....
        docker run -it ..... /bin/bash

2. Creamos una imagen:

        docker build -t josedom24/web:v1 .

        docker run --name servidorweb -d -p 80:80 josedom24/web:v1

3. Modificamos aplicación
4. Distribuimos la aplicación

### Kubernetes

### OpenShift

