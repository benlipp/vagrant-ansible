# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.
  config.vm.box = "ubuntu/trusty64"
  for i in 0..2
    name = "box_#{i}"
    config.vm.define name do |box|
      box.vm.box_url = "bento/ubuntu-16.04"
      box.vm.network :private_network, ip: "192.168.56.10#{i}"
      ssh_port = "10#{i}22".to_i
      box.vm.network :forwarded_port, guest: 22, host: ssh_port, id: "ssh"
      box.vm.provider :virtualbox do |v|
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--memory", 512]
        v.customize ["modifyvm", :id, "--name", "web"]
      end
    end
  end
end
