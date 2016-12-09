# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "dharmab/centos7"
  
  # Share the Ansible playbook for self-provisioning
  config.vm.synced_folder "ansible/", "/ansible/", owner: "root",
    group: "root", mount_options: ["dmode=755", "fmode=644"]

  # Setup Yum
  config.vm.provision "shell", inline: "yum -y update"

  # Script which bootstraps Ansible
  config.vm.provision "shell", path: "ansible/bootstrap.sh", run: "always"

end
