# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.box = "geerlingguy/centos7" #CentOS 7
  config.vm.network "private_network", ip: "192.168.123.123"

  config.vm.provision "shell", inline: <<-SHELL
  sudo sed -i 's/enforcing/disabled/g' /etc/selinux/config
  sudo sestatus
  yum update -y
  SHELL
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 4
  end
  config.vm.provision:reload
end

