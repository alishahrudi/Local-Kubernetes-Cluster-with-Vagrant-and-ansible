# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    # General Vagrant VM configuration.
    config.vm.box = "ubuntu/bionic64"
    config.ssh.insert_key = false
    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.provider :virtualbox do |v|
        v.memory = 512
        v.linked_clone = true
    end

    config.vm.define "master" do |app|
        app.vm.hostname = "kub-master.dev"
        app.vm.network :private_network, ip: "192.168.60.10"
        app.vm.provider :virtualbox do |v|
            v.customize ["modifyvm", :id, "--memory", "2048"]	
        end
    end

    # Application server 2.
    config.vm.define "node1" do |app|
        app.vm.hostname = "kube-node1.dev"
        app.vm.network :private_network, ip: "192.168.60.11"
    end
    # Database server.
    config.vm.define "node2" do |db|
        db.vm.hostname = "kube-node2.dev"
        db.vm.network :private_network, ip: "192.168.60.12"
    end
    # Application server 2.
    config.vm.define "node3" do |app|
        app.vm.hostname = "kube-node3.dev"
        app.vm.network :private_network, ip: "192.168.60.13"
    end
    # Database server.
    config.vm.define "node4" do |db|
        db.vm.hostname = "kube-node4.dev"
        db.vm.network :private_network, ip: "192.168.60.14"
    end
end
