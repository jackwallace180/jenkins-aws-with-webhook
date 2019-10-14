
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision "shell", path: "environment/provision.sh"
  config.vm.network "private_network", ip: "192.168.10.200"

end
