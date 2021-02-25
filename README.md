# Entorno Vagrant aprovisionado con Ansible para una integración con Drupal y CKAN.

## Requerimientos
* Virtualbox
* Vagrant

## Instrucciones de montaje

Para montar el entorno seguimos los siguientes pasos:

1. `git clone git@github.com:managume/vagrant-drupal-ckan`
2. Editamos el archivo `ansible/vars.yml` con los credenciales que queramos utilizar.
3. Levantamos Vagrant lanzando `vagrant up --provision`.
4. Para restablecer la máquina virtual lanzar `vagrant destroy -f` y a continuación `vagrant up --provision`.