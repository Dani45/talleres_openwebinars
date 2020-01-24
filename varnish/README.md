# Aumento de rendimiento en la ejecución de PHP con varnish

Partimos de la instalación de apache2 con el módulo PHP y wordpress instalado.

1. Comprobamos que estamos en prefork y que tenemos el módulo

        apache2ctl -V
        apache2ctl -M

