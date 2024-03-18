# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2204"
  config.vm.host_name = "postgresql"

  # PostgreSQL Server static IP
  config.vm.network :private_network,
                    :ip => "192.168.254.42"

  # Provisioning
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provision.yml"
    ansible.extra_vars = {
      pg_version: "14",
      databases: [
        { name: "db1", owner: "user1", password: "password1" },
        { name: "db2", owner: "user2", password: "password2" }
      ]
    }
  end  
end
