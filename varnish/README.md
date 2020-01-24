# Aumento de rendimiento en la ejecución de PHP con varnish

Partimos de la instalación de apache2 con el módulo PHP y wordpress instalado.

1. Comprobamos que estamos en prefork y que tenemos el módulo

        apache2ctl -V
        apache2ctl -M

    Podemos ver también la información de PHP (`info.php`).

2. Realizamos una prueba de rendimiento desde el host:

        ab -t 10 -c 200 -k http://varnish.local/wordpress/index.php

    Sale una media de unas 90 # / seg.

3. Instalamos `fpm-php`:

        a2dismod php7.3

        apt install php7.3-fpm php7.3

        a2enmod proxy_fcgi setenvif

        a2enconf php7.3-fpm

        a2dismod mpm_prefork 
        a2enmod mpm_event

4. Comprobamos que estamos en event, `info.php`, y que tenemos procesos `fpm-php`.

         ps -A|grep fpm

5. Realizamos una prueba de rendimiento desde el host:

        ab -t 10 -c 200 -k http://varnish.local/wordpress/index.php

    Nos da unas 120 #/seg

6. Actualmente tenemos `fpm-php` usando un socket linux, podríamos tener configurado para que escuchara por un puerto TCP, para ello en el fichero `/etc/php/7.3/fpm/pool.d/www.conf`:

        listen = 127.0.0.1:9000

    Y en la configuración de apache2, en el fichero `/etc/apache2/conf-available/php7.3-fpm.conf`:

        SetHandler "proxy:fcgi://127.0.0.1:9000"

    Reinicio apache2 y fpm-php. 

7. Con nginx:

        systemctl stop apache2
        apt install nginx

    Configuramos para que use `fpm-php` con socket linux, en el fichero `/etc/nginx/sites-available/default`:

        fastcgi_pass unix:/var/run/php/php7.3-fpm.sock;

    Y añadimos esta configuración al estar en un subdirectorio:

         location /wordpress {
                rewrite ^(/[^/]+)?(/wp-.*) /wordpress/$2 break;
                rewrite ^/wordpress/(.*)$ /wordpress/index.php?q=$1 last;
        }
8. Comprobamos que estamos en nginx y hacemos una prueba:

        ab -t 10 -c 200 -k http://varnish.local/wordpress/index.php

    Nos da unos 150 #/seg

