# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

hosts = {
"dj-lb"    => "192.168.33.70",
"django01" => "192.168.33.71",
"django02" => "192.168.33.72",
"db01"	   => "192.168.33.75",
}

Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true
  hosts.each do |name, ip|
    config.vm.define name do |machine|
        machine.vm.box = "ubuntu/trusty64"
        machine.vm.hostname = "%s" % name
        machine.vm.network :private_network, ip: ip
        #machine.ssh.private_key_path = "~/.ssh/id_rsa"
        #machine.vm.synced_folder ".", "/vagrant", id: "vagrant-root", disabled: true
        machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.memory = 4096
	  v.cpus = 2
	  #v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        end
	#machine.vm.provision "ansible" do |ansible|
        #	ansible.playbook = "site.yml"
    	#end

     end
   end
end


