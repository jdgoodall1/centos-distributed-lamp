# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "web" do |web|
    web.vm.box = "bento/centos-7.5"
    web.vm.hostname = 'web'
    web.vm.network "private_network", ip: "192.168.33.10"
    web.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "provisioners/web_main.yml"
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "bento/centos-7.5"
    db.vm.hostname = 'db'
    db.vm.network "private_network", ip: "192.168.33.20"
    db.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "provisioners/db_main.yml"
    end
  end

end