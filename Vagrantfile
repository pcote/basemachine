# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false 
    vb.memory = "512"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.extra_vars = {
        host: "all",
        mysql_root_password: "setRootPasswordHere",
    }
    ansible.playbook = "main_playbook.yml"
  end 
end
