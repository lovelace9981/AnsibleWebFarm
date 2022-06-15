# -*- mode: ruby -*-
 # vi: set ft=ruby :

 VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
# General Vagrant VM configuration.
config.ssh.insert_key = true
# config.ssh.private_key_path = "~/.ssh/id_rsa"
config.ssh.forward_agent = true
config.nfs.functional = false

config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/authorized_keys"
config.vm.provision "shell", inline: <<-EOC
    echo "nameserver 8.8.8.8" > /etc/resolv.conf
    sudo ip route del default via 192.168.121.1
    sudo ip route add default via 192.168.100.1
    echo "finished"
 EOC

  config.vm.provider :libvirt do |libvirt|
    libvirt.cpus = 4
    libvirt.memory = 2048
    libvirt.cputopology :sockets => '1', :cores => '2', :threads => '2'
    libvirt.driver = "kvm"
  #  libvirt.storage_pool_name = "DISK_IMG"
  end

  # Web Server 1
  config.vm.define :m1 do |app|
    app.vm.box = "generic/debian11"
    app.vm.hostname = "m1.swapfinal"



     app.vm.network "private_network", ip: "192.168.100.4", netmask: "255.255.255.0", libvirt__network_name: "ansible", libvirt__dhcp_enabled: false, libvirt__host_ip: '192.168.100.1'

     # app.vm.provision "ansible" do |ansible|
     #   ansible.limit = "all"
     #   ansible.verbose= "v"
     #   ansible.playbook = "playbooks/webserverplaybook.yml"
     # end
  end


  # Web Server 2
  config.vm.define :m2 do |app|
    app.vm.box = "generic/debian11"
    app.vm.hostname = "m2.swapfinal"

     app.vm.network "private_network", ip: "192.168.100.5", netmask: "255.255.255.0", libvirt__network_name: "ansible", libvirt__dhcp_enabled: false, libvirt__host_ip: '192.168.100.1'

     # app.vm.provision "ansible" do |ansible|
     #   ansible.limit = "all"
     #   ansible.verbose= "v"
     #   ansible.playbook = "playbooks/webserverplaybook.yml"
     # end
  end

  # Web Server 3
  config.vm.define :m3 do |app|
    app.vm.box = "generic/debian11"
    app.vm.hostname = "m3.swapfinal"

     app.vm.network "private_network", ip: "192.168.100.6", netmask: "255.255.255.0", libvirt__network_name: "ansible", libvirt__dhcp_enabled: false, libvirt__host_ip: '192.168.100.1'

     # app.vm.provision "ansible" do |ansible|
     #   ansible.limit = "all"
     #   ansible.verbose= "v"
     #   ansible.playbook = "playbooks/webserverplaybook.yml"
     # end
  end

  # Web Server 4
  config.vm.define :m4 do |app|
    app.vm.box = "generic/debian11"
    app.vm.hostname = "m4.swapfinal"

     app.vm.network "private_network", ip: "192.168.100.7", netmask: "255.255.255.0", libvirt__network_name: "ansible", libvirt__dhcp_enabled: false, libvirt__host_ip: '192.168.100.1'

     # app.vm.provision "ansible" do |ansible|
     #   ansible.limit = "all"
     #   ansible.verbose= "v"
     #   ansible.playbook = "playbooks/webserverplaybook.yml"
     # end
  end


  # Web Server 3
  config.vm.define :m5 do |app|
    app.vm.box = "generic/debian11"
    app.vm.hostname = "m5.swapfinal"

     app.vm.network "private_network", ip: "192.168.100.8", netmask: "255.255.255.0", libvirt__network_name: "ansible", libvirt__dhcp_enabled: false, libvirt__host_ip: '192.168.100.1'

     # app.vm.provision "ansible" do |ansible|
     #   ansible.limit = "all"
     #   ansible.verbose= "v"
     #   ansible.playbook = "playbooks/webserverplaybook.yml"
     # end
  end


  # Web Server 3
  config.vm.define :m6 do |app|
    app.vm.box = "generic/debian11"
    app.vm.hostname = "m3.swapfinal"

     app.vm.network "private_network", ip: "192.168.100.9", netmask: "255.255.255.0", libvirt__network_name: "ansible", libvirt__dhcp_enabled: false, libvirt__host_ip: '192.168.100.1'

     # app.vm.provision "ansible" do |ansible|
     #   ansible.limit = "all"
     #   ansible.verbose= "v"
     #   ansible.playbook = "playbooks/webserverplaybook.yml"
     # end
  end

  # LoadBalancer
  config.vm.define :m0 do |lb|
    lb.vm.box = "generic/debian11"
    lb.vm.hostname = "m0.swapfinal"

     lb.vm.network "private_network", ip: "192.168.100.2", netmask: "255.255.255.0", libvirt__network_name: "ansible", libvirt__dhcp_enabled: false, libvirt__host_ip: '192.168.100.1'

     # lb.vm.provision "ansible" do |ansible|
     #   ansible.limit = "all"
     #   ansible.verbose= "v"
     #   ansible.playbook = "playbooks/loadbalancerplaybook.yml"
     # end
  end


  # DB server
  config.vm.define :db1 do |db|
    db.vm.box = "rockylinux/8"
    db.vm.hostname = "m20.swapfinal"

     db.vm.network "private_network", ip: "192.168.100.20", netmask: "255.255.255.0", libvirt__network_name: "ansible", libvirt__dhcp_enabled: false, libvirt__host_ip: '192.168.100.1'

     # db.vm.provision "ansible" do |ansible|
     #   ansible.limit = "all"
     #   ansible.verbose= "v"
     #   ansible.playbook = "playbooks/databaseplaybook.yml"
     # end
  end

  # DB server
  config.vm.define :db2 do |db|
    db.vm.box = "rockylinux/8"
    db.vm.hostname = "m21.swapfinal"

     db.vm.network "private_network", ip: "192.168.100.21", netmask: "255.255.255.0", libvirt__network_name: "ansible", libvirt__dhcp_enabled: false, libvirt__host_ip: '192.168.100.1'

    # db.vm.provision "ansible" do |ansible|
    #   ansible.limit = "all"
    #    ansible.verbose= "v"
    #    ansible.playbook = "playbooks/databaseplaybook.yml"
    # end
  end
end
