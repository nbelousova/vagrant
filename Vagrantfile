# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.env.enable
  config.vm.define "droplet1" do |config|
      config.vm.provider :digital_ocean do |provider, override|
        override.ssh.private_key_path = '~/.ssh/id_rsa'
        override.vm.box = 'digital_ocean'
        override.vm.box_url = "https://github.com/devopsgroup-io/vagrant-digitalocean/raw/master/box/digital_ocean.box"
        override.nfs.functional = false
        provider.ssh_key_name = ENV['key_name']
        provider.token = ENV['DO_token']
        provider.image = 'ubuntu-16-04-x64'
        provider.region = 'nyc1'
        provider.size = '512mb'
        provider.private_networking = true
      end
      config.vm.provision "ansible" |ansible|
       ansible-playbook = "calc-sum.yml"
      end

  end
    config.vm.define "droplet2" do |config|
      config.vm.provider :digital_ocean do |provider, override|
        override.ssh.private_key_path = '~/.ssh/id_rsa'
        override.vm.box = 'digital_ocean'
        override.vm.box_url = "https://github.com/devopsgroup-io/vagrant-digitalocean/raw/master/box/digital_ocean.box"
        override.nfs.functional = false
        provider.ssh_key_name = ENV['key_name']
        provider.token = ENV['DO_token']
        provider.image = 'ubuntu-16-04-x64'
        provider.region = 'nyc1'
        provider.size = '512mb'
        provider.private_networking = true
      end
      config.vm.provision "ansible" |ansible|
       ansible-playbook = "calc-front.yml"
      end


  end

  config.vm.synced_folder ".", "/vagrant", disabled: true

end
