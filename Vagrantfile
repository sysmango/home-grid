# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  #config.vm.box = "ubuntu/xenial64"
  config.vm.box = "opensuse/openSUSE-Tumbleweed-x86_64"
  # config.vm.box_check_update = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider "virtualbox" do |v|
    v.memory = 512
  end

  config.vm.define "manager" do |manager1|
    manager1.vm.hostname = "manager"
    manager1.vm.network "private_network", ip: "192.168.33.11"
    manager1.vm.provision :shell, inline: "sed 's/127\.0\.0\.1.manager/192\.168\.33\.11 manager/' -i /etc/hosts"
    # node.vm.network "forwarded_port", guest: 80, host: 8080
  end

  # config.vm.define "worker2" do |worker2|
  #   worker2.vm.hostname = "worker2"
  #   worker2.vm.network "private_network", ip: "192.168.33.12"
  #   worker2.vm.provision :shell, inline: "sed 's/127\.0\.0\.1.manager/192\.168\.33\.12 manager/' -i /etc/hosts"
  #   # node.vm.network "forwarded_port", guest: 80, host: 8080   
  # end

  config.vm.define "worker" do |worker|
    worker.vm.hostname = "worker"
    worker.vm.network "private_network", ip: "192.168.33.13"
    worker.vm.provision :shell, inline: "sed 's/127\.0\.0\.1.manager/192\.168\.33\.13 worker/' -i /etc/hosts"
    # node.vm.network "forwarded_port", guest: 80, host: 8080
    worker.vm.provision "ansible" do |ansible|
      ansible.playbook = "site.yml"
      #ansible.playbook = "swarm-facts.yml"
      ansible.limit = "all"
      ansible.extra_vars = {
         swarm_iface: "enp0s8"
       }
    #ansible.verbose = "v"
      ansible.groups = {
        "docker-manager" => ["manager"],
        "docker-worker"  => ["worker"],
      }
    end
  end  
end
