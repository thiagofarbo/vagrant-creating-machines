Vagrant.configure("2") do |config|

  config.vm.define "m1" do |m1|
    m1.vm.box = "ubuntu/focal64"
    m1.vm.provider :virtualbox do |vb|
      vb.name = "m1"
    end
    m1.vm.network "private_network", ip: "192.168.1.255"
    m1.vm.network :forwarded_port, guest: 22, host: 2223, id: "ssh"
    m1.ssh.port = 2223
    m1.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)"
  end

  config.vm.define "m2" do |m2|
    m2.vm.box = "centos/8"
    m2.vm.provider :virtualbox do |vf|
      vf.name = "m2"
      # vf.vmx["memsize"] = "1024"
    end
    m2.vm.network "private_network", ip: "192.168.1.61"
    m2.vm.network :forwarded_port, guest: 22, host: 2201, id: "ssh"
    m2.ssh.port = 2201
    m2.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)"
  end

  config.vm.define "m3" do |m3|
    m3.vm.box = "ubuntu/focal64"
    m3.vm.provider :virtualbox do |lv|
      lv.name = "m3"
      # lv.driver = 'kvm'
    end
    m3.vm.network "private_network", ip: "192.168.1.62"
    m3.vm.network :forwarded_port, guest: 22, host: 2202, id: "ssh"
    m3.ssh.port = 2202
    m3.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)"
  end

end
