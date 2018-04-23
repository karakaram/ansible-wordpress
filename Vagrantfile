# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "bento/centos-7.4"

  # config.ssh.insert_key = false
  # config.ssh.forward_agent = true
  config.vm.box_check_update = false
  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false
  end
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end

  config.vm.define "wordpress" do |vm|
    vm.vm.hostname = "wordpress"
    vm.vm.network "private_network", ip: "192.168.33.11"
    vm.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "1024"
      vb.cpus = "2"
    end
    vm.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "site.yml"
      # ansible.playbook = "wordpress/bootstrap.yml"
      ansible.inventory_path = "vagrant"
      ansible.limit = "all"
      # ansible.tags = [""]
    end
  end

end
