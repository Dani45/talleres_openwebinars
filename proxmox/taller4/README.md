# Taller 4: Gestión de usuarios y permisos en Proxmox VE

## Fuentes de autentificación

* **Linux PAM Standard Authentication**: Serían usuarios físicos del servidor Proxmox. Por ejemplo, el usuario root que hemos usado en el curso sería de este tipo. Estos usuarios pueden conectar la consola del servidor (opción Shell) y acceder por ssh al servidor.
* **Proxmox VE Authentication Server**: No son usuarios físicos del servidor. Se usan cuando el usuario no es necesario que acceda al servidor Proxmox. En este caso, los usuarios están totalmente gestionados por Proxmox VE y pueden cambiar sus propias contraseñas a través de la GUI.

## Algunos conceptos

* Usuarios y grupos
* Permisos: Nos permite gestionar las acciones permitidas a usuarios o grupos.
* Roles: Agrupación de permisos
* Pools de recursos: Conjunto de máquinas virtuales, contenedores y fuente de almacenamiento. 

## Gestión de Permisos

* Un **privilegio** es el derecho a realizar una acción específica.
* Las listas de privilegios se agrupan en **roles**.

### Privilegios

### Roles

## Asignación de permisos

Los permisos (roles) se asignan a un usuario o grupo y a un objeto (máquina virtual/contenedor, fuente de almacenamiento, pool de recursos, ...).


## Práctica

* [Introducción a la gestión de usuarios](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo8/introduccion.md)
