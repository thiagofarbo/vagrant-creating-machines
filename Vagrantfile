Vagrant.configure("2") do |config|

  config.vm.define "m1" do |m1|
    m1.vm.box = "ubuntu/focal64"
    m1.vm.provider :virtualbox do |vb|
      vb.name = "m1"
    end
    m1.vm.network "forwarded_port", guest: 80, host: 8080
  end

  config.vm.define "m2" do |m2|
    m2.vm.box = "centos/8"
    m2.vm.provider :vmware_fusion do |vf|
      vf.name = "m2"
      vf.vmx["memsize"] = "1024"
    end
    m2.vm.network "forwarded_port", guest: 80, host: 8081
  end

  config.vm.define "m3" do |m3|
    m3.vm.box = "ubuntu/focal64"
    m3.vm.provider :libvirt do |lv|
      lv.name = "m3"
      lv.driver = 'kvm'
    end
    m3.vm.network "forwarded_port", guest: 80, host: 8082
  end

end
