# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # vagrant dns; requires `vagrant plugin install landrush`
  config.landrush.enabled = true
  config.landrush.tld = "vm"

  # postgres node
  config.vm.define "postgres" do |postgres|
    postgres.vm.box = "bento/ubuntu-16.04"
    postgres.vm.hostname = "postgres.vm"
    postgres.vm.network "private_network", ip: "10.5.50.5"

    postgres.ssh.forward_agent = true
    postgres.ssh.insert_key = false

    postgres.vm.provider "virtualbox" do |v|
        v.memory = "4096"
    end
  end

  # django webapp
  config.vm.define "catchpy" do |catchpy|
    catchpy.vm.box = "bento/ubuntu-16.04"
    catchpy.vm.hostname = "catchpy.vm"
    catchpy.vm.network "private_network", ip: "10.5.50.6"

    catchpy.ssh.forward_agent = true
    catchpy.ssh.insert_key = false

    catchpy.vm.provider "virtualbox" do |v|
        v.memory = "4096"
    end
  end

end
