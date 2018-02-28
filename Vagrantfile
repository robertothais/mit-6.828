# -*- mode: ruby -*-                                                                                │
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y build-essential
    apt-get install -y gcc-multilib
    apt-get install -y git
    apt-get install -y qemu
    apt-get install -y gdb
    apt-get install -y python
  SHELL

  config.vm.provider 'virtualbox' do |v|
    v.name = "mit-6.828"
    v.customize ['modifyvm', :id, '--uartmode1', 'disconnected']
  end

  config.vm.synced_folder ".", "/home/vagrant/lab"
end
