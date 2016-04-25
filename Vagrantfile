# -*- mode: ruby -*-
# vi: set ft=ruby :
# Sample Vagranfile to setup Learning Environment
# for Ansible Playbook Essentials
Vagrant.configure(2) do |config|
  config.vm.box = 'ubuntu/trusty64'

  config.vm.define 'control' do |control|
    control.vm.network :private_network, ip: '192.168.61.10'
    control.vm.provision :ansible do |ansible|
      ansible.playbook = 'provision_vagrant.yml'
    end
  end

  config.vm.define 'db' do |db|
    db.vm.network :private_network, ip: '192.168.61.11'
  end

  config.vm.define 'dbel' do |db|
    db.vm.network :private_network, ip: '192.168.61.14'
    db.vm.box = 'opscode_centos-6.5-i386'
    db.vm.box = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5_chef-provisionerless.box'
  end

  config.vm.define 'www' do |www|
    www.vm.network :private_network, ip: '192.168.61.12'
  end

  config.vm.define 'lb' do |lb|
    lb.vm.network :private_network, ip: '192.168.61.13'
  end
end
