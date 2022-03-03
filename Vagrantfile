#Vagrant.configure("2") do |config|
#  config.vm.box = "generic/rhel8"
#end
#
#
#
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
 	# General Vagrant VM configuration.
 	config.vm.box = "generic/rocky8"
 	config.ssh.insert_key = false
 	config.vm.synced_folder ".", "/vagrant", disabled: true
 	config.vm.provider :virtualbox do |v|
		v.memory = 512
 		v.linked_clone = true
	end

	# Web server 1.
	config.vm.define "webserver1" do |web_servers|
		web_servers.vm.hostname = "webserver1.example.com"
		web_servers.vm.network :private_network, ip: "192.168.60.4"
	end

	# Web server 2.
	config.vm.define "webserver2" do |web_servers|
		web_servers.vm.hostname = "webserver2.example.com"
		web_servers.vm.network :private_network, ip: "192.168.60.5"
	end

	# Haproxy server or loadbalancer
	config.vm.define "loadbalancer1" do |loadbalancers|
		loadbalancers.vm.hostname = "loadbalancer.example.com"
		loadbalancers.vm.network :private_network, ip: "192.168.60.6"
	end
end
