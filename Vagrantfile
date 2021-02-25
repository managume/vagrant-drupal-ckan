# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "s2city"

  config.vm.network :forwarded_port, guest: 80, host: 80
  config.vm.network :forwarded_port, guest: 8983, host: 8983
  config.vm.network :forwarded_port, guest: 5432, host: 5432

  config.vm.synced_folder "src/drupal", "/var/www/html/drupal"
  config.vm.synced_folder "src/ckan/configuration", "/etc/ckan/default"
  config.vm.synced_folder "src/ckan/project", "/usr/lib/ckan/default/src/ckan/ckan"
  config.vm.synced_folder "src/ckan/extensions", "/usr/lib/ckan/default/src/ckan/ckanext"
  
  config.vm.provision :ansible_local do |ansible|
    ansible.become = true
    ansible.config_file="ansible/ansible.cfg"
    ansible.playbook = "ansible/playbook.yml"
  end
end
