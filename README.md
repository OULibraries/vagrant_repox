# Repox VM using Vagrant and Virtualbox

##  Notes

This Ansible Playbook will install a Repox Development Environment using Vagrant and Virtualbox. The Repox application is proxied to port 443. Login credentials for both the proxy login and Repox login are set in 'my-vars.yml'

## Requirements

* Requires [Ansible](http://docs.ansible.com/ansible/intro_installation.html)
* Requires [Vagrant](https://www.vagrantup.com/downloads.html). 
* Requires [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
 

## Installation

1. Clone this repo to a local folder.
2. Copy `my-vars.default.yml` to `my-vars.yml` and insert your particulars.
3. Modify your local machine's hosts file to include 'repox.vagrant.dev' for 10.255.255.10.
4. Execute the following command: `vagrant up`.
5. Point your favorite browser to https://repox.vagrant.dev and login twice using the credentials you set in my-vars.yml.

## Usage 

The following vagrant commands are likely to see the most use. 

* `vagrant up` to start the vm. The box will build itself on first startup. 
* `vagrant ssh` to log in
* `vagrant halt` to shut the VM Down
* `vagrant reload` bounces the box

It maybe be neccessary to do a `halt` or `reload` if the guest VM gets confused about its network, or loses its fileshares. This most frequently happens when the host machine goes to sleep and/or moves between networks.

Less frequently, you'll may want to reprovision to get the lastest changes, or rebuild your VM Completely. In that case, you'll need these commands:

* `vagrant provision` will re-run the ansible provisioners
* `vagrant destroy` to delete the VM, in case you want to start over

## Dependencies

* [OU Libraries Centos7 Role](https://github.com/OULibraries/ansible-role-centos7)
* [OU LIbraries Repox Role](https://github.com/OULibraries/ansible-role-repox)
* [OU Libraries Apache2 Role](https://github.com/OULibraries/ansible-role-apache2)
* [OU Libraries Users Role](https://github.com/OULibraries/ansible-role-users)


