# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "s2city"

  # PROXY HTTP (NGINX)
  config.vm.network :forwarded_port, guest: 80, host: 80
  # PROXY HTTPS (NGINX)
  config.vm.network :forwarded_port, guest: 443, host: 443
  # APACHE (DRUPAL)
  config.vm.network :forwarded_port, guest: 8000, host: 8000
  # SOLR (TOMCAT)
  config.vm.network :forwarded_port, guest: 8983, host: 8983
  # POSTGRESQL
  config.vm.network :forwarded_port, guest: 5432, host: 5432

  config.vm.synced_folder "src/drupal", "/var/www/html/", create: true
  config.vm.synced_folder "src/ckan/configuration", "/etc/ckan/default", create: true
  config.vm.synced_folder "src/ckan/project", "/usr/lib/ckan/default/src/ckan/ckan", create: true
  config.vm.synced_folder "src/ckan/extensions", "/usr/lib/ckan/default/src/ckan/ckanext", create: true
  
  config.vm.provision :ansible_local do |ansible|
    ansible.become = true
    ansible.config_file = "ansible/ansible.cfg"
    ansible.playbook = "ansible/playbook.yml"
  end
end
