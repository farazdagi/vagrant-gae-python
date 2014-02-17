# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    # Application Server
    config.vm.box = "precise64"
    config.vm.box_url = "http://files.vagrantup.com/precise64.box"
    config.vm.hostname = "memberbase"
    config.vm.network :private_network, ip: "10.1.0.30"
    config.vm.synced_folder "./", "/project", type: "nfs"

    # Enable provisioning with Ansible
    config.vm.provision :ansible do |ansible|
        ansible.playbook = "devops/site.yml"
        ansible.inventory_path = "devops/hosts"
        #ansible.verbose = "v"
    end

    # Provider(s) configuration
    config.vm.provider "virtualbox" do |v|
      v.memory = 1024
    end
end
