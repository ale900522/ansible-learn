# -*- mode: ruby -*-
# vi: set ft=ruby :
# This is optimized for Vagrant 1.7 and above.
# Although versions 1.6.x should behave very similarly, it is recommended
# to upgrade instead of disabling the requirement below.
Vagrant.require_version ">= 1.7.0"

Vagrant.configure("2") do |config|

  # config.vm.box = "generic/debian12"
  # Disable the new default behavior introduced in Vagrant 1.7, to
  # ensure that all Vagrant machines will use the same SSH key pair.
  # See https://github.com/hashicorp/vagrant/issues/5005
  config.ssh.insert_key = false
  config.ssh.private_key_path = ["~/.vagrant.d/insecure_private_key"]

  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider :virtualbox do |v|

      v.memory = 512
      v.cpus = 1
      v.linked_clone = true
      # change the network card hardware for better performance
      v.customize ["modifyvm", :id, "--nictype1", "virtio" ]
      v.customize ["modifyvm", :id, "--nictype2", "virtio" ]
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      # v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
      v.customize ["modifyvm", :id, "--vram", 64]
      # multicore
      v.customize ["modifyvm", :id, "--ioapic", "on"]
  end
  #############################################INITIAL SERVER CONFIG####################################################################

   # Application server-00.
   config.vm.define "server00" do |server00|
    server00.vm.box = "generic/debian12"
    server00.vm.hostname = "srv-server-00"
    server00.vm.network :public_network, :bridge=>"enp5s0", ip: "192.168.1.200", use_dhcp_assigned_default_route: false, hostname: true
    # server00.vm.network :private_network, ip: "192.168.56.5"

  end
  # Application server-01.
  config.vm.define "server01" do |server01|
    server01.vm.box = "generic/debian12"
    server01.vm.hostname = "srv-server-01"
    server01.vm.network :public_network, :bridge=>"enp5s0", ip: "192.168.1.201", use_dhcp_assigned_default_route: false, hostname: true
    # server01.vm.network :private_network, ip: "192.168.56.6"

  end

   # Application server-02.
  config.vm.define "server02" do |server02|
    server02.vm.box = "generic/debian12"
    server02.vm.hostname = "srv-server-02"
    server02.vm.network :public_network, :bridge=>"enp5s0", ip: "192.168.1.202", use_dhcp_assigned_default_route: false, hostname: true
    # server02.vm.network :private_network, ip: "192.168.56.7"
 end

   # Application server-03.
  config.vm.define "server03" do |server03|
    server03.vm.box = "generic/debian12"
    server03.vm.hostname = "srv-server-03"
    server03.vm.network :public_network, :bridge=>"enp5s0", ip: "192.168.1.203", use_dhcp_assigned_default_route: false, hostname: true
    # server03.vm.network :private_network, ip: "192.168.56.8"

  end
  # Application server-04.
  config.vm.define "server04" do |server04|
    server04.vm.box = "generic/debian12"
    server04.vm.hostname = "srv-server-04"
    server04.vm.network :public_network, :bridge=>"enp5s0", ip: "192.168.1.204", use_dhcp_assigned_default_route: false, hostname: true
    # server04.vm.network :private_network, ip: "192.168.56.9"

  end

   # Application server-05.
  config.vm.define "server05" do |server05|
    server05.vm.box = "bento/rockylinux-10"
    server05.vm.hostname = "srv-server-05"
    server05.vm.network :public_network, :bridge=>"enp5s0", ip: "192.168.1.205", use_dhcp_assigned_default_route: false, hostname: true
    # server05.vm.network :private_network, ip: "192.168.56.10"
 end

   # Application server-06.
  config.vm.define "server06" do |server06|
    server06.vm.box = "bento/rockylinux-10"
    server06.vm.hostname = "srv-server-06"
    server06.vm.network :public_network, :bridge=>"enp5s0", ip: "192.168.1.206", use_dhcp_assigned_default_route: false, hostname: true
    # server06.vm.network :private_network, ip: "192.168.56.11"

  end
####################################################################################################3333
# Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  #config.vm.provision 'shell', inline: <<-SHELL
   #   echo -e '\\033[1;33mthis vagrant machine is ready\\033[0;39m'
  #SHELL

end
