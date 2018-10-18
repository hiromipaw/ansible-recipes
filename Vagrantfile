# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

ENV['ANSIBLE_ROLES_PATH'] = "#{File.dirname(__FILE__)}/../"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # VirtualBox.
  config.vm.provider :virtualbox do |v|
    v.memory = 512
    v.cpus = 1
  end

  # Debian Stretch
  config.vm.define "stretch" do |stretch|
    stretch.vm.hostname = "stretch"
    stretch.vm.box = "debian/stretch64"

    # Ansible.
    stretch.vm.provision "ansible" do |ansible|
      ansible.playbook = "vagrant.yml"
      ansible.sudo = true
    end
  end
end
