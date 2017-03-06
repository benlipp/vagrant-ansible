# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com
  config.vm.box = "bento/ubuntu-16.04"

  config.vm.define "maul" do |box|
    box.vm.box_url = "bento/ubuntu-16.04"
    box.vm.network :private_network, ip: "192.168.56.100"
    box.vm.network :forwarded_port, guest: 22, host: 10022, id: "ssh"
    box.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "va-maul"]
    end
  end

  config.vm.define "tyranus" do |box|
    box.vm.box_url = "bento/ubuntu-16.04"
    box.vm.network :private_network, ip: "192.168.56.101"
    box.vm.network :forwarded_port, guest: 22, host: 10122, id: "ssh"
    box.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "va-tyranus"]
    end
  end

  config.vm.define "sidious" do |box|
    box.vm.box_url = "bento/ubuntu-16.04"
    box.vm.network :private_network, ip: "192.168.56.102"
    box.vm.network :forwarded_port, guest: 22, host: 10222, id: "ssh"
    box.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "va-sidious"]
    end
  end

  config.vm.define "balancer" do |box|
    box.vm.box_url = "bento/ubuntu-16.04"
    box.vm.network :private_network, ip: "192.168.56.103"
    box.vm.network :forwarded_port, guest: 22, host: 10322, id: "ssh"
    box.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "va-balancer"]
    end
  end


end
