# Despliegue de aplicaciones PHP en Heroku

## Objetivos

* Conocer el concepto de Cloud Computing
* Introducir la capa de Plataforma como Servicio (PaaS)
* Conocer las características principales de Heroku
* Usar git como herramienta fundamental en el despliegue moderno de aplicaciones
* Preparar nuestras aplicaciones PHP para ser desplegadas en Heroku
* Poner en práctica el despliegue de algunas aplicaciones PHP en Heroku

## Nivel

Intermedio

## ¿Qué aprenderás en el taller?

* Las características fundamentales del Cloud Computing
* Las ventajas que nos ofrece el PaaS en el despliegue de aplicaciones
* Las características fundamentales de Heroku
* Usar el dashboard y el CLI de heroku
* Uso básico de git como medio de transferencia de ficheros en nuestro despliegue
* Desplegar aplicaciones PHP en Heroku

## Conocimientos previos

* Uso básico de git
* Conocimientos previos sobre protocolo HTTP, servicios web (apache/nginx) y servidor de base de datos MySql
* Algún conocimiento de PHP (no vamos a codificar, pero si modificaremos alguna línea de código).
* Conocimientos muy básico de linux (el taller se impartirá usando este sistema operativo), aunque se puede hacer usando cualquier otro sistema operativo.

## Desarrollo

### Despliegue de una aplicación PHP con heroku dashboard

Repositorio: https://github.com/josedom24/heroku_php

Se despliega con apache2 y a continuación se cambia a nginx y se vuelve a desplegar.

### Ciclo de vida de una aplicación PHP en heroku

Repositorio: https://github.com/josedom24/heroku_bookmedik

* Vamos a añadir un addons de ClearDB Mysql.
* Vemos que se ha creado una variable de entorno: `mysql usurio:password@server/bd`
* Cargamos el esquema de la base de dato: `mysql -u user -ppassword -h server bd < schema.sql
* Probamos con `database.php`, poniendo los datos estáticamente.
* Comprobamos que la aplicación está funcionando

**Entorno de desarrollo/producción**

* Modifico `database.php` para que si estamos en horoku lea y parsee la variable de entorno, y si estamos en local ponga una configuración estática de la base de datos.
* Comprobamos que funciona en local y desplegamos en heroku.

**Despliegue automáticos**

* Configuramos los despliegues automáticos.
* Realizamos un cambio en la página, la probamos en local y comprobamos que se ha desplegado de forma automática.

### Despliegue de un CMS en heroku

* Instalar heroku CLI

        heroku login -i
        
        cd wp-jose/
        git init

* Copia los ficheros del repo clonado (https://github.com/technomile/Heroku-WordPress)

        git add *
        // Dentro del directorio    
        heroku apps:create wp-jose
    
        git remote -v
        heroku	https://git.heroku.com/wp-jose.git (fetch)
        heroku	https://git.heroku.com/wp-jose.git (push)

        git commit -am "primer commit"

        heroku apps:info wp-jose

* Base de datos
  
        heroku addons:add cleardb
        heroku config

* Miro wl wp-config.php para ver como se parsea la variable de entorno
* Instalamos plugin "WP Offload Media Lite"

