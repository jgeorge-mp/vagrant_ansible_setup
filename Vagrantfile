Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "echo Hello"

  config.vm.define "node01" do |node01|
    node01.vm.box = "generic/ubuntu2104"
    node01.vm.hostname = "node01"
    node01.vm.network "private_network", ip: "192.168.56.11", 
       name: "vboxnet0"

    node01.vm.provider "virtualbox" do |vb|
       vb.memory = 1024
       vb.cpus = 1
    end
    node01.vm.provision "ansible" do |ansible|
        ansible.playbook = "common.yml"
    end
  end

  config.vm.define "node02" do |node02|
    node02.vm.box = "generic/centos7"
    node02.vm.hostname = "node02"
    node02.vm.network "private_network", ip: "192.168.56.12",
       name: "vboxnet0"

    node02.vm.provider "virtualbox" do |vb|
       vb.memory = 1024
       vb.cpus = 1
    end

    node02.vm.provision "ansible" do |ansible|
        ansible.playbook = "common.yml"
    end

  end


  config.vm.define "node03" do |node03|
    node03.vm.box = "generic/rhel7"
    node03.vm.hostname = "node03"
    node03.vm.network "private_network", ip: "192.168.56.13",
       name: "vboxnet0"
    node03.vm.provider "virtualbox" do |vb|
       vb.memory = 1024
       vb.cpus = 1
    end

    node03.vm.provision "ansible" do |ansible|
        ansible.playbook = "common.yml"
    end
  end


end

