# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Common configuration
  config.vm.box = "centos/7"
  config.vm.synced_folder "./", "/vagrant", type: "rsync", disabled: false

  # Rancher master
  config.vm.define "rancher-master" do |master|
    master.vm.network :private_network, ip: "192.168.168.100", dhcp_enabled: false
    master.vm.hostname = "rancher-master.local"

    master.vm.provider "virtualbox" do |v|
        v.name = "rancher-master"
        v.memory = 2028
        v.cpus = 1
    end

    master.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "rancher-master.yml"
      ansible.verbose = true
      ansible.install_mode = :pip
    end    
  end

  # Single rancher worker
  config.vm.define "rancher-worker" do |worker|
    worker.vm.network :private_network, ip: "192.168.168.101", dhcp_enabled: false
    worker.vm.hostname = "rancher-worker01.local"
    worker.vm.provider "virtualbox" do |v|
        v.name = "rancher-worker"
        v.memory = 2048
        v.cpus = 2
    end

    worker.vm.provision "ansible" do |ansible|
      ansible.playbook = "rancher-worker.yml"
    end         
  end
  
end
