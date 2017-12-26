# -*- mode: ruby -*-
# vi: set ft=ruby :
$script = <<SCRIPT
SCRIPT


if Gem::Version.new(::Vagrant::VERSION) < Gem::Version.new('1.5')
  Vagrant.require_plugin('vagrant-hostmanager')
end

Vagrant.configure('2') do |config|

  if ENV.key? 'VAGRANT_BOX'
    config.vm.box = ENV['VAGRANT_BOX']
  else
    config.vm.box = 'centos/7'
  end

  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true

  config.vm.define :server do |server|
    server.vm.hostname = 'server'
    server.vm.network :private_network, :ip => '10.0.5.2'
    server.vm.provision "shell", inline: $script
  end

  config.vm.define :edge1 do |server|
    server.vm.hostname = 'node1'
    server.vm.network :private_network, :ip => '10.0.5.3'
    server.vm.provision "shell", inline: $script
  end

  config.vm.define :edge2 do |server|
    server.vm.hostname = 'node2'
    server.vm.network :private_network, :ip => '10.0.5.4'
    server.vm.provision "shell", inline: $script
  end

  config.vm.define :edge3 do |server|
    server.vm.hostname = 'node3'
    server.vm.network :private_network, :ip => '10.0.5.5'
    server.vm.provision "shell", inline: $script
  end

end

