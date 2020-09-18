# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrant Settings
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.box_check_update = false
  config.vm.network "private_network", ip: "192.168.99.10"
  config.disksize.size = "40GB" # You need install plugin vagrant-disksize on vagrant. For this, do vagrant plugin install vagrant-disksize.
  config.vm.provision "shell", inline: <<-SHELL
    apt update -y && apt upgrade -y
    L='br' && sudo sed -i 's/XKBLAYOUT=\"\w*"/XKBLAYOUT=\"'$L'\"/g' /etc/default/keyboard
  SHELL

  #Virtualbox Settings
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.name = "BootCamp | Ubuntu_20.04"
    vb.memory = "1024"
    vb.cpus = "1"
  end
end
