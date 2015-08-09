# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
    
    config.vm.box = "ubuntu/trusty64"
    config.vm.boot_timeout = 60
    
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 512
        vb.cpus = 1
    end

    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "provision/install.yml"
        ansible.host_key_checking = false
        ansible.sudo = true
        ansible.tags = ['common', 'jenkins']
    end
    
    config.vm.network "forwarded_port", host: 8080, guest: 80, auto_correct: true
    config.vm.network "forwarded_port", host: 8081, guest: 8080, auto_correct: true
    
end


