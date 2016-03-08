# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "172.17.0.100"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  config.vm.synced_folder "salt/roots/", "/srv/salt/"
  config.vm.provision :salt do |salt|
    salt.minion_config = "salt/minion"
    salt.masterless = true
    salt.run_highstate = true
  end
end
