Vagrant.configure("2") do |config|
 
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.synced_folder ".", "/vagrant"
  config.vm.provider "virtualbox" do |v|
    v.linked_clone = true
    v.memory = 1024
    v.cpus = 1
  end  
  
  config.vm.define "web" do |web|
    web.vm.hostname = "web"
    web.vm.network "private_network", ip: "192.168.50.5";
  end  

  config.vm.define "web2" do |web2|
    web2.vm.hostname = "web2"
    web2.vm.network "private_network", ip: "192.168.50.6";    
  end  

  config.vm.define "mdb" do |mdb|
    mdb.vm.hostname = "masterdb"
    mdb.vm.network "private_network", ip: "192.168.50.7";
  end

  config.vm.define "sdb" do |sdb|
    sdb.vm.hostname = "slavedb"
    sdb.vm.network "private_network", ip: "192.168.50.8";
  end
  
  config.vm.define "loadb" do |loadb|
    loadb.vm.hostname = "loadb"
    loadb.vm.network "private_network", ip: "192.168.50.10";
    # loadb.vm.provision "ansible" do |ansible|
    #   ansible.playbook = "master_playbook.yml"
    # end
  end

end