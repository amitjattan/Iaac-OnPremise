# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false
    config.vm.synced_folder '.', '/vagrant', type: 'nfs'
  
    # VirtualBox.
    # `vagrant up virtualbox --provider=virtualbox`
    
    config.vm.define "apache" do |virtualbox|
      virtualbox.vm.hostname = "apache"
      virtualbox.vm.box = "ubuntu1604"
	  virtualbox.ssh.username = "vagrant"
	  virtualbox.ssh.password = "vagrant"
      virtualbox.vm.network :private_network, ip: "192.168.2.11"
  
      config.vm.provider :virtualbox do |v|
        v.gui = false
        v.memory = 512
        v.cpus = 1
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--ioapic", "on"]
      end
     #
     # Run Ansible from the Vagrant Host
     #
      config.vm.provision "shell", inline: <<-SHELL
	 ansible-playbook /vagrant/ansible/apache.yml
      SHELL
    end
end
