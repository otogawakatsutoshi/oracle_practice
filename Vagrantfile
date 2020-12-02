# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
    # The most common configuration options are documented and commented below.
    # For a complete reference, please see the online documentation at
    # https://docs.vagrantup.com.
  
    # Every Vagrant development environment requires a box. You can search for
    # boxes at https://vagrantcloud.com/search.
    config.vm.box = "oraclelinux/7"

    # The url from where the 'config.vm.box' box will be fetched if it
    # doesn't already exist on the user's system.
    config.vm.box_url = "https://oracle.github.io/vagrant-projects/boxes/oraclelinux/7.json"

    # Disable automatic box update checking. If you disable this, then
    # boxes will only be checked for updates when the user runs
    # `vagrant box outdated`. This is not recommended.
    # config.vm.box_check_update = false
  
    # Create a forwarded port mapping which allows access to a specific port
    # within the machine from a port on the host machine. In the example below,
    # accessing "localhost:8080" will access port 80 on the guest machine.
    # NOTE: This will enable public access to the opened port
    # config.vm.network "forwarded_port", guest: 3000, host: 3000
    config.vm.network "forwarded_port", guest: 1521, host: 1521
    # Express Managerのポート
    config.vm.network "forwarded_port", guest: 5500, host: 5500
    config.vm.network "forwarded_port", guest: 80, host: 8080
  
    # Create a forwarded port mapping which allows access to a specific port
    # within the machine from a port on the host machine and only allow access
    # via 127.0.0.1 to disable public access
    # config.vm.network "forwarded_port", guest: 3000, host: 3000, host_ip: "127.0.0.1"
  
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    # config.vm.network "private_network", ip: "192.168.33.10"
  
    # Create a public network, which generally matched to bridged network.
    # Bridged networks make the machine appear as another physical device on
    # your network.
    # config.vm.network "public_network"
  
    # Share an additional folder to the guest VM. The first argument is
    # the path on the host to the actual folder. The second argument is
    # the path on the guest to mount the folder. And the optional third
    # argument is a set of non-required options.
    
    # this is require vagrant-vbguest plugin
    config.vm.synced_folder "./oracle_dev_setup", "/vagrant_oracle_dev_setup", type:"virtualbox"
    config.vm.synced_folder "./oracle_data_load", "/home/vagrant/oracle_data_load", type:"virtualbox"
    config.vm.synced_folder "./python3", "/home/vagrant/python3", type:"virtualbox"
    config.vm.synced_folder "./java", "/home/vagrant/java", type:"virtualbox"
    config.vm.synced_folder "./csharp", "/home/vagrant/csharp", type:"virtualbox"
    config.vm.synced_folder "./fsharp", "/home/vagrant/fsharp", type:"virtualbox"
    config.vm.synced_folder "./golang", "/home/vagrant/golang", type:"virtualbox"
    config.vm.synced_folder "./php", "/home/vagrant/php", type:"virtualbox"
    config.vm.synced_folder "./rust", "/home/vagrant/rust", type:"virtualbox"
    config.vm.synced_folder "./rlang", "/home/vagrant/rlang", type:"virtualbox"
    config.vm.synced_folder "./scala", "/home/vagrant/scala", type:"virtualbox"

    # Provider-specific configuration so you can fine-tune various
    # backing providers for Vagrant. These expose provider-specific options.
    # Example for VirtualBox:
    #
    config.vm.provider "virtualbox" do |vb|
      # Display the VirtualBox GUI when booting the machine
      # vb.gui = true

      # Customize the amount of memory on the VM:
      if vb.gui then
        vb.memory = "4096"
      else
        vb.memory = "2048"
      end
    end
    #
    # View the documentation for the provider you are using for more
    # information on available options.
  
    # Enable provisioning with a shell script. Additional provisioners such as
    # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
    # documentation for more information about their specific syntax and use.
    config.vm.provision "shell", path: "./provision.sh"
end
  