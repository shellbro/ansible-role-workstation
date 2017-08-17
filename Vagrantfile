Vagrant.configure("2") do |config|
  config.vbguest.auto_update = false
  
  config.vm.define "centos" do |centos|
    centos.vm.box = "centos/7"
    centos.vm.provider "virtualbox" do |v|
      v.cpus = 2
      v.memory = 2048
    end
    centos.vm.provision "ansible" do |a|
      a.limit = "all"
      a.playbook = "tests/test-vagrant.yml"
      a.verbose = false
    end
    centos.vm.synced_folder ".", "/vagrant", disabled: true
  end
end
