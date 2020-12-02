# -*- mode: ruby -*-
# vi: set ft=ruby :

# For a complete reference, please see the online documentation at
# https://docs.vagrantup.com.
# This example taken from www.ansibletutorials.com

Vagrant.configure(2) do |config|

  config.vm.box = "bento/ubuntu-18.04"

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus   = 1
  end
  
# SSH Default Configuration
# Commented because you shouldn't need to copy them.
# config.ssh.username         = "root"
# config.ssh.password         = "vagrant"
# config.ssh.port             = 22
# config.ssh.insert_key       = true
# config.ssh.private_key_path = "~/.ssh/id_rsa"
# config.ssh.forward_agent    = true

# Provision with Ansible
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
      #ansible.tags = "tests"
    end
end
