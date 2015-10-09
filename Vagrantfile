# -*- mode: ruby -*-
# vi: set ft=ruby :

#Vagrant::Config.run do |config|
Vagrant.configure(2) do |config|
#  config.vm.box = "debian-607-x64-vbox4210"
#  config.vm.box_url = "http://puppet-vagrant-boxes.puppetlabs.com/debian-607-x64-vbox4210.box"
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 8080, host: 8081
  config.vm.network "forwarded_port", guest: 5000, host: 5000
  config.vm.network "forwarded_port", guest: 9000, host: 9000
  config.vm.provision :puppet do |puppet|
    puppet.module_path      = "modules"
    puppet.manifests_path  = "manifests"
    puppet.manifest_file      = "init.pp"
  end
  config.vm.provision "shell", inline: <<-SHELL
 	wget -O- https://toolbelt.heroku.com/install-ubuntu.sh | sh
  SHELL
end
