# Taller 1: Introducción a Proxmox VE y despliegue de máquinas virtuales

## Introducción a la virtualización con Proxmox VE

**Virtualización**: Nos permite ejecutar más de un sistema virtual, y múltiples sistemas operativos y aplicaciones, en un solo servidor, aumentando el rendimiento del hardware disponible e incrementando el tiempo de procesamiento de un equipo.

Tipos:

* **Virtualización completa**: El hipervisor **simula** un hardware suficiente para permitir que un sistema operativo no adaptado se ejecute de forma aislada. 
* **Virtualización ligera**: O también llamada virtualización a nivel de sistema operativo, o virtualización basada en contenedores. Es un método de virtualización en el que, sobre el núcleo del sistema operativo se ejecuta una capa de virtualización que permite que existan múltiples instancias aisladas de espacios de usuario (**Contenedor**). Por lo tanto, un contenedor es un conjunto de procesos aislado, que se ejecuta en un servidor, y que accede a un sistema de ficheros propio, tiene una configuración red propio y accede a los recursos del host (memoria y CPU).	

**Proxmox Virtual Environment**, o Proxmox VE es un entorno de virtualización de servidores de código abierto. Es una distribución de GNU/Linux basada en Debian que permite el despliegue y la gestión de máquinas virtuales y contenedores.

La versión actual de Proxmox VE nos permite gestionar los siguientes recursos virtualizados:

* **Máquinas virtuales**: Para ello utiliza virtualización completa con el uso del hipervisor KVM.
* **Contenedores**: Podemos gestionar contenedores de sistema LXC.

## Algunos consideraciones a la hora de la instalación de Proxmox VE

* Escenarios para la instalación de Proxmox VE
* Laboratorio de pruebas:

	La configuración recomendada para la máquina virtual sería:
	
	* 8 Gb de RAM
	* 100 Gb de disco duro
	* 4 núcleos de CPU

	Configuración especifica de VirtualBox para la instalación de Proxmox

## GUI de Proxmox

* [Vista general de Proxmox VE](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo2/vista_general.md)
* [Introducción al clúster Proxmox VE](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo2/introduccion_cluster.md)
* [Almacenamiento y redes disponibles](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo2/almacenamiento_redes.md)

## Máquinas virtuales

* Subo una ISO a Proxmox.
* [Creación de máquinas virtuales Linux](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo3/creacion_linux.md)
* [Gestión de máquinas virtuales](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo3/gestion.md)
* [Características y hardware de las máquinas virtuales](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo3/caracteristicas.md)
* [Creación de máquinas virtuales Windows](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo3/creacion_windows.md)
	
