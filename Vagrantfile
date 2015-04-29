# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.provider "virtualbox" do |virtualbox|
    virtualbox.memory = 512
    virtualbox.cpus = 1
  end

  config.vm.box = "http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-amd64-vagrant-disk1.box"

  config.vm.network "private_network", type: "dhcp"

  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true

  config.vm.provision "puppet" do |puppet|
    puppet.manifests_path = "manifests"
    puppet.module_path = "modules"
    puppet.options = "--show_diff"
  end
end
