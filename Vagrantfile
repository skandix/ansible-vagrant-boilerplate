# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/lunar64"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.network "private_network", ip: "192.168.60.66"
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 4
  end

#  config.vm.cloud_init :user_data do |cloud_init|
#    cloud_init.content_type = "text/cloud-config"
#    cloud_init.path = "cloud-init.yml"
#  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "site.yml"
  end
end
