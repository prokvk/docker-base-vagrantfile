# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "debian/jessie64"

  #Set your own port forwarding here
  #config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.synced_folder "./data", "/data"
  config.vm.synced_folder "./dockerfiles", "/dockerfiles"

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y git
    sudo wget -qO- https://get.docker.com/ | sh
    sudo usermod -aG docker vagrant
  SHELL
end
