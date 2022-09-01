# DevOps_Project
## Repositorio de proyectos de DevOps

Proyecto secuencial de herramientas de DevOps, con el objetivo de adquirir experiencia en el campo.
Es un trabajo que consta de varias partes, cada una con una herramienta diferente.

1. **Primer Paso**:
Aprovisionamiento de infraestructura utilizando Vagrant, primer paso en IaaC.

*Documentación*:
Se procede a la instalación de Vagrant y VM Box dentro del dispositivo de trabajo, se genera un repositorio nuevo con dos Branches, agregando una de desarrollo denominada "dev".

Se genera un Vagrantfile para el aprovisionamiento de la infraestructura, detallando un servidor de control y tres nodos de trabajo. Se modifican los hostnames, direcciones IP y conexiones SSH.

También se detallan configuraciones como apertura de puertos, cantidad de núcleos y memoria a asignar.

Se ejecuta el archivo mediante el comando *vagrant up*

Se genera dentro de la carpeta el archivo host con los datos de dirección IP y nombre de host.

Mediante conexión SSH al servidor de control, se controla que el archivo se encuentre dentro de la carpeta.
