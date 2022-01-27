# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # config.vm.box = "gbailey/amzn2"
  config.vm.box = "ubuntu"

  config.vm.box_check_update = true

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  config.vm.network "forwarded_port", guest: 2375, host: 2375, host_ip: "127.0.0.1"
  
  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "1024"
  end

  # Enable provisioning with an Ansible playbook.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end

end
