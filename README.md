# Entorno Vagrant aprovisionado con Ansible para una integración con Drupal y CKAN.

## Descripción del entorno

En el directorio `ansible` se encuentra:
* El archivo `vars.yml` con los credenciales por defecto.
* El archivo `playbook.yml` contiene la definición de nuestro sistema.
* El archivo `ansible.cfg` contiene variables de configuración de Ansible
* El directorio `config` contiene archivos necesarios a la hora de desplegar el sistema.

El archivo `Vagrantfile` es el archivo de definición de Vagrant que construirá nuestra máquina virtual.

Por otra parte tenemos en `src` la estructura de carpetas de trabajo:
* En el directorio `drupal` tendremos el código de Drupal
* En el directorio `ckan` nos encontramos tres subcarpetas:
  * La carpeta `configuration` donde podemos encontrar los archivos de configuración, concretamente el `ckan.ini` con la configuración de CKAN.
  * La carpeta `extensions` donde tendremos las diferentes extensiones del tipo *ckanext-extension*.
  * La carpeta `project` con el código core de CKAN.

## Instrucciones de montaje

Para montar el entorno seguimos los siguientes pasos:

1. Nos clonamos el repositorio.
2. Entramos en la carpeta ansible del repositorio y editamos el archivo `vars.yml` con los credenciales que queramos utilizar.
3. Eliminamos todos los `.gitkeep` de los subdirectorios de `/src`.
4. Levantamos Vagrant lanzando `vagrant up`

## Comandos útiles