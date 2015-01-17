# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos7"
  config.vm.box_url = "https://f0fff3908f081cb6461b407be80daf97f07ac418.googledrive.com/host/0BwtuV7VyVTSkUG1PM3pCeDJ4dVE/centos7.box"

  config.vm.provider :virtualbox do |vb|
    vb.gui = true
  end

  # config.vm.network "forwarded_port", guest: 80, host: 18080

  config.vm.provision "shell", :inline => <<-EOT
    yum -y update; yum clean all
    yum -y install epel-release; yum clean all
    yum -y upgrade; yum clean all
    yum -y install docker-io
    chkconfig docker on
    service docker start
  EOT
end
