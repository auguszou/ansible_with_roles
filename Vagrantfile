# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.provision "shell", inline: "sudo locale-gen en_US.UTF-8"

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "ubuntu-14.04"
    ubuntu.vm.network "private_network", ip: "192.168.56.2"
    ubuntu.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.inventory_path = "ansible_hosts.vagrant"
      ansible.host_key_checking = false
      ansible.extra_vars = { ssh_user: 'vagrant' }
    end
  end

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

end
