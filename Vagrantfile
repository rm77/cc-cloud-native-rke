# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  #onfig.vm.network "forwarded_port", guest: 22, host: 30022
  config.vm.network "public_network"
  config.vm.define "vm1" do |myvm|
    myvm.vm.box = "generic/ubuntu2010"
    myvm.vm.hostname = "vm1"
    myvm.vm.provider :virtualbox do |vb|
       vb.memory = 512
       vb.cpus = 2
    end
    myvm.vm.provision "shell",inline: <<-SHELL
       Y=$(cat /etc/passwd | grep user1 | wc -l)
       [[ $Y -lt 1 ]] && sudo useradd user1 -puser1password -m || echo "ada"
    SHELL
    myvm.vm.network :public_network, ip: "10.199.9.103"
  end
  config.vm.define "vm2" do |myvm|
    myvm.vm.box = "generic/ubuntu2010"
    myvm.vm.hostname = "vm2"
    myvm.vm.provider :virtualbox do |vb|
       vb.memory = 512
       vb.cpus = 2
    end
    myvm.vm.provision "shell",inline: <<-SHELL
       Y=$(cat /etc/passwd | grep user1 | wc -l)
       [[ $Y -lt 1 ]] && sudo useradd user1 -puser1password -m || echo "ada"
    SHELL
    myvm.vm.network :public_network, ip: "10.199.9.104"
  end
  config.vm.define "vm3" do |myvm|
    myvm.vm.box = "generic/ubuntu2010"
    myvm.vm.hostname = "vm3"
    myvm.vm.provider :virtualbox do |vb|
       vb.memory = 512
       vb.cpus = 2
    end
    myvm.vm.provision "shell",inline: <<-SHELL
       Y=$(cat /etc/passwd | grep user1 | wc -l)
       [[ $Y -lt 1 ]] && sudo useradd user1 -puser1password -m || echo "ada"
    SHELL
    myvm.vm.network :public_network, ip: "10.199.9.105"
  end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
