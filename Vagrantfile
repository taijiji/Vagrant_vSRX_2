# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
    config.vm.box = "juniper/ffp-12.1X47-D15.4-packetmode"  
    config.vm.define :vsrx1 do | vsrx1 |
        vsrx1.vm.hostname = 'vsrx1'
        vsrx1.vm.network "private_network",ip: "192.168.33.2",netmask: "255.255.255.0"
        vsrx1.vm.network "private_network",ip: "192.168.35.1",netmask: "255.255.255.252",virtualbox__intnet: "PNI"
    end
    config.vm.define :vsrx2 do | vsrx2 |
        vsrx2.vm.hostname = 'vsrx2'
        vsrx2.vm.network "private_network",ip: "192.168.34.2",netmask: "255.255.255.0"
        vsrx2.vm.network "private_network",ip: "192.168.35.2",netmask: "255.255.255.252",virtualbox__intnet: "PNI"
    end
end