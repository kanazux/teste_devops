# -*- mode: ruby -*-
# vi: set ft=ruby

Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  config.vm.network :public_network
  config.vm.hostname =  "prometheus.local"

  config.ssh.insert_key = false

  config.vm.provider "virtualbox" do |vb|
    vb.memory = 4096
    vb.cpus = 4
  end

  config.vm.provision :ansible do |ans|
    ans.playbook = "yml/playbook.yml"
    ans.become = true
  end
end
