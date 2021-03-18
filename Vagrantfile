# -*- mode: ruby -*-
# vi: set ft=ruby :

$centos_script = <<-SCRIPT
mv /etc/yum.repos.d /etc/yum.repos.d.orig.$(date -Iseconds)
mkdir -p /etc/yum.repos.d/
curl -sSLo /etc/yum.repos.d/CentOS-Base.repo http://mirrors.cloud.tencent.com/repo/centos7_base.repo
# sed "s/keepcache=0/keepcache=1/" -i /etc/yum.conf
# yum install -y git yum-utils
SCRIPT

# VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(2) do |config|
    config.vm.define "server1" do |s|
        s.vm.box = "centos/7"
        # s.vm.box_url = "http://files.saas.hand-china.com/vagrant/bento_centos-7.8.box"
        s.vm.hostname = "server1"
        s.vm.network "private_network", ip: "192.168.56.11"
        # s.vm.network "forwarded_port", guest: 6443, host: 6443
        # s.vm.network "forwarded_port", guest: 8443, host: 8443
        s.vm.synced_folder ".", "/vagrant", disabled: true
        # s.vm.provision "shell", inline: $centos_script
        s.vm.provider "virtualbox" do |v|
            v.memory = 4096
            v.cpus = 2
        end
    end
    config.vm.define "server2" do |s|
        s.vm.box = "centos/7"
        # s.vm.box_url = "http://files.saas.hand-china.com/vagrant/bento_centos-7.8.box"
        s.vm.hostname = "server2"
        s.vm.network "private_network", ip: "192.168.56.12"
        s.vm.synced_folder ".", "/vagrant", disabled: true
        # s.vm.provision "shell", inline: $centos_script
        s.vm.provider "virtualbox" do |v|
            v.memory = 4096
            v.cpus = 2
        end
    end
    config.vm.define "server3" do |s|
        s.vm.box = "centos/7"
        # s.vm.box_url = "http://files.saas.hand-china.com/vagrant/bento_centos-7.8.box"
        s.vm.hostname = "server3"
        s.vm.network "private_network", ip: "192.168.56.13"
        s.vm.synced_folder ".", "/vagrant", disabled: true
        # s.vm.provision "shell", inline: $centos_script
        s.vm.provider "virtualbox" do |v|
            v.memory = 4096
            v.cpus = 2
        end
    end
    config.vm.define "server4" do |s|
        s.vm.box = "centos/7"
        # s.vm.box_url = "http://files.saas.hand-china.com/vagrant/bento_centos-7.8.box"
        s.vm.hostname = "server4"
        s.vm.network "private_network", ip: "192.168.56.14"
        s.vm.synced_folder ".", "/vagrant", disabled: true
        # s.vm.provision "shell", inline: $centos_script
        s.vm.provider "virtualbox" do |v|
            v.memory = 4096
            v.cpus = 2
        end
    end

  # Ansible provisioner.
  # config.vm.provision :ansible do |ansible|
  #   ansible.playbook = "init-loan.yml"
  # end
end
