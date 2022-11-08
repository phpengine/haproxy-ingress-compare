# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  bridge_interface = ENV['BRIDGE'] || "wlp3s0"

  config.vm.box = "ubuntu/focal64"

  config.vm.box_check_update = false

  config.vm.network "public_network", bridge: bridge_interface

  config.vm.provider "virtualbox" do |vb|
    vb.cpus  = "4"
    vb.memory = "4096"
  end

#   config.vm.provision "ansible" do |ansible|
#     ansible.playbook = "playbook-install.yml"
#   end
#
#   config.vm.provision "ansible" do |ansible|
#     ansible.playbook = "playbook-configure.yml"
#     ansible.extra_vars = {
#       bridge_interface: bridge_interface
#     }
#   end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook-test.yml"
  end

end
