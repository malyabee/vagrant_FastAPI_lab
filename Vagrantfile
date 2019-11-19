# -*- mode: ruby -*-
# vi: set ft=ruby :


# update OS and install docker 
$commonscript = <<-SCRIPT
sudo yum update -y
sudo echo "LANG=en_US.utf-8" > /etc/environment
sudo echo "LC_ALL=en_US.utf-8" >> /etc/environment
sudo yum install git jq net-tools -y
sudo yum -y groupinstall development
sudo yum -y install python36u
sudo yum -y install python36u-pip
sudo yum -y install python36u-devel
SCRIPT

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
    config.vm.define "fastapi_lab" do |fastapi_lab|
      # Every Vagrant development environment requires a box. You can search for
      # boxes at https://vagrantcloud.com/search.         
         fastapi_lab.vm.box = "centos/7"
        
        
        fastapi_lab.vm.network "forwarded_port", guest: 8000, host: 8000
         # Memory and CPU allocation
         fastapi_lab.vm.provider "virtualbox" do |v|
            v.memory = 512
            v.cpus = 1
         end
         # Create a forwarded port mapping which allows access to a specific port
         # within the machine from a port on the host machine and only allow access
         # via 127.0.0.1 to disable public access
        
         # Host name allocation
         fastapi_lab.vm.hostname = "fastapilab.example.com"

         # Installing required packages for docker  node
        fastapi_lab.vm.provision "shell", inline: $commonscript
       
         
         # Share an additional folder to guest VM.  The first argument is the path on the hst to the actual folder. 
         # The Second argument is the path on the guest to mount the floder
        
   end
end
