
Vagrant.configure('2') do |config_vm|
  config_vm.vm.define "prometheus" do |config|
    config.vm.provider :digital_ocean do |provider, override|
      override.ssh.private_key_path = '~/.ssh/caterpy_do'
      override.vm.box = 'digital_ocean'
      override.vm.box_url = "https://github.com/devopsgroup-io/vagrant-digitalocean/raw/master/box/digital_ocean.box"
      override.nfs.functional = false
      provider.token = 'e437e36d84d25a47d520e47f2e104b236b2f401f3fc197080266ac6c9c78d381'
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
