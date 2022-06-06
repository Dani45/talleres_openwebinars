# Taller 2: Gestión del almacenamiento en Proxmox VE

## Introducción al almacenamiento en Proxmox VE

Proxmox VE nos permite distintas **fuentes de almacenamiento** para alojar el contenido de los discos de nuestras máquinas virtuales y contenedores, y de los discos adicionales en su caso.

## Tipos de almacenamiento

Hay dos clases de almacenamiento que podemos configurar:

* **Sistemas de ficheros**: Nos permiten el acceso a un sistema de ficheros.
* **Dispositivos de bloque**: Este tipo de almacenamiento nos ofrece dispositivos de bloques, que posteriormente podremos formatear y utilizar. 

## Almacenamiento compartido

Algunas de las fuentes de almacenamiento que podemos usar tienen la característica de poder compartir la información entre distintos nodos de nuestro clúster Proxmox VE. En el caso que utilicemos estos tipos de almacenamiento tendremos a nuestra disposición la funcionalidad de migración en vivo y alta disponibilidad. 

## Snapshots

Algunas de las fuentes de almacenamiento que podemos usar tienen la característica de poder realizar instantáneas (snapshots). De esta manera podremos guardar el estado de un disco en un determinado momento, y si es necesario podremos volver a ese estado a posteriori.

## Aprovisionamiento ligero

Todas las fuentes de almacenamiento que nos permiten la realización de instantáneas, también nos proporcionan la funcionalidad del aprovisionamiento ligero. Podemos crear discos de un tamaño, pero lo ocupado realmente en el disco duro aumentará cuando la MV vaya guardando información.

## Resumen de los tipos de las fuentes de almacenamiento

## ¿Qué podemos guardar en las distintas fuentes de almacenamiento?

* **Disk image**: Imágenes de discos para las máquinas virtuales.
* **Containers**: Sistema de ficheros de los contenedores Linux.
* **ISO image**: Imágenes ISO.
* **Container template**: Plantillas de contenedores.
* **VZDump backup files**: Ficheros de copia de seguridad.

## Parte práctica

* [Creación de una fuente de almacenamiento de tipo Directory](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo4/directory.md)
* [Añadir nuevos discos a una máquina virtual](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo4/nuevo_almacenamiento.md)
* [Gestión de los discos de una máquina virtual](https://github.com/iesgn/curso_proxmox_cep/blob/main/modulo4/gestion_almacenamiento.md)
