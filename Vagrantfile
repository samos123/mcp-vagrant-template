# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  config.vm.provider "virtualbox" do |vb|
     # Display the VirtualBox GUI when booting the machine
     vb.gui = true

     # Customize the amount of memory on the VM:
     vb.memory = "4096"
  end

  config.vm.define "cfg01" do |cfg01|
    cfg01.vm.box = "ubuntu/xenial64"
    cfg01.vm.provision "shell" do |s|
        s.path = "bootstrap-salt-master.sh"
        s.env = { node_name: "cfg01.{{environment_name}}.local",
                  reclass_address: "{{reclass_model_git_repo}}",
                  reclass_branch: "master" }
    end
    cfg01.vm.provision "file", source: "deploy_key", destination: "/root/.ssh/id_rsa"
    # The private_network should be cfg01 deploy_address and single_address
    # this depends on the model
    cfg01.vm.network "private_network", ip: "{{cfg01_address}}"
  end

end
