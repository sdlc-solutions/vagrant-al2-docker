# Vagrantfile to use for Docker

This Vagrantfile and Ansible playbook will install Docker on the guest OS and expose the daemon over port 2375 from the guest to host OS.  Inside the vagrantfile you can select either AmazonLinux2 or Ubuntu as the base guest OS.

### Vagrantfile

    Vagrant.configure("2") do |config|

    # config.vm.box = "gbailey/amzn2" # AmazonLinux2
    config.vm.box = "ubuntu"          # Ubuntu

    ...

### playbook.yml
The Ansible playbook uses 2 'blocks' to determine which OS is in the guest, and installs the appropriate package.  This playbook can theoretcially translate to other images and use-cases as needed.

## How to use

    git clone https://github.com/sdlc-solutions/vagrant-al2-docker.git vagrant-docker
    cd vagrant-docker
    vagrant up

Once vagrant completes, on host:

    export DOCKER_HOST=tcp://localhost:2375

This will point the local Docker client to the Vagrantbox.