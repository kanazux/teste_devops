
Vagrant.configure('2') do |config_vm|
  config_vm.vm.define "prometheus" do |config|
    config.vm.provider :digital_ocean do |provider, override|
      override.ssh.private_key_path = ''
      override.vm.box = 'digital_ocean'
      override.vm.box_url = "https://github.com/devopsgroup-io/vagrant-digitalocean/raw/master/box/digital_ocean.box"
      override.nfs.functional = false
      provider.token = ''
      provider.image = 'debian-9-x64'
      provider.region = 'nyc1'
      provider.size = 's-2vcpu-2gb'
    end
    config.vm.provision :ansible do |ans|
      ans.playbook = 'yml/playbook.yml'
      ans.become = true
    end
  end
end
