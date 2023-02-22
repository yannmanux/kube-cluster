# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "master-node" do |master|
    master.vm.box = "centos/7"
    master.vm.network "private_network", ip: "192.168.33.10"
    master.vm.provider "virtualbox" do |vb|
      vb.name = "master-node"
      vb.memory = "1024"
      vb.cpus = "1"
    end
  end

  (1..3).each do |i|
    config.vm.define "worker-node-#{i}" do |worker|
      worker.vm.box = "centos/7"
      worker.vm.network "private_network", ip: "192.168.33.#{i + 10}"
      worker.vm.provider "virtualbox" do |vb|
        vb.name = "worker-node-#{i}"
        vb.memory = "1024"
        vb.cpus = "1"
      end
    end
  end
end
