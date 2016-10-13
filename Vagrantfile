# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "geerlingguy/centos7"
  #config.vm.network "private_network", ip: "10.255.255.10"
  #config.vm.hostname = "repox.vagrant.dev"
  config.vm.network "forwarded_port", guest:8080, host:8080 # Tomcat
  # config.vm.network "forwarded_port", guest:80, host:80 # Apache
  config.vm.network "forwarded_port", guest:443, host:8443 # Apache


  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
  end
  
  # We use a shell provisioner instead of an Ansible provisioner because of Windows
  config.vm.provision "shell",
    path: "bootstrap.sh", keep_color: "True"
end
