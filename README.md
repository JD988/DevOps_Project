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

Mediante conexión SSH al servidor de control, se controla que el archivo se encuentre dentro de la carpeta, y se copia el archivo a */etc/hosts* para que se logre la resolución de nombres.

1. **Segundo Paso**:
Configuración de dispositivos utilizando Ansible. Segundo paso en IaaC.

*Documentación*:
Comprobamos la capacidad de conexión de SSH mediante el comando vagran@*nombrenodo* , utilizando *vagrant* como contraseña.

Generamos una llave SSH.

ssh-keygen
ssh-copy-id nodo1 && ssh-copy-id nodo2 && ssh-copy-id nodo3

*Además al tener un keygen, no necesitamos suministrar una contraseña*


Procedemos a instalar Ansible en **control**:

sudo apt-get install ansible -y

*Existe la posibilidad de que tengamos un error al intentar instarl, para lo cual primero debemos ejecutar sudo apt-get install*

Luego vamos a generar una carpeta nueva para los archivos de Ansible, ya que es necesario que sepa a quien apuntar para las configuraciones.

Esto se puede realizar con archivos comunes o con archivos yaml.

Antes de ejecutar el playbook, debemos asegurarnos la conectividad con un comando ad-hoc desde el directorio:

ansible nodes -i *nombre* -m command -a hostname

*Se lee como Ansible a todos los nodos obtenidos del inventario de este archivo, dale el módulo comando con argumento hostname*