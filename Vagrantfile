BOX_IMAGE = "hashicorp/bionic64"
NODE_COUNT = 2


Vagrant.configure("2") do |config|
  config.vm.define "master" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "master"
    subconfig.vm.network "private_network", ip: "192.168.56.10", name: "VirtualBox Host-Only Ethernet Adapter"
  end
  
  (1..NODE_COUNT).each do |i|
    config.vm.define "node#{i}" do |subconfig|
      subconfig.vm.box = BOX_IMAGE
      subconfig.vm.hostname = "node#{i}"
      # subconfig.vm.network "forwarded_port", guest: 80, host: 8080
      subconfig.vm.network "private_network", ip: "192.168.56.#{i + 10}", name: "VirtualBox Host-Only Ethernet Adapter"
    end
  end
end
