# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "lab01" do |lab01|
         lab01.vm.box = "centos/7"
         lab01.vm.hostname = "laboratorio"
         lab01.vm.network  "public_network" , brigde: "eth0 Wi-Fi Intel(R) Dual Band Wireless-AC 8265", nat: false, ip: "192.168.1.105", hostname: true , auto_config: false
         lab01.vm.disk :disk, size: "20GB", primary: true
      lab01.vm.provider "virtualbox" do |vb|
         vb.memory = "1024"
         vb.cpus = "2"
       lab01.vm.provision "shell" , inline:      
             "sudo yum install wget vim -y
              sudo yum remove docker \
              docker-client \
              docker-client-latest \
              docker-common \
              docker-latest \
              docker-latest-logrotate \
              docker-logrotate \
              docker-engine
              sudo yum install yum-utils -y
              sudo yum-config-manager \
              --add-repo \
              https://download.docker.com/linux/centos/docker-ce.repo
              sudo yum-config-manager --enable docker-ce-nightly
              sudo yum install docker-ce docker-ce-cli containerd.io -y
              sudo yum install docker -y
              sudo systemctl start docker
              sudo systemctl enable docker
              sudo docker run hello-world
              DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}
              mkdir -p $DOCKER_CONFIG/cli-plugins
              curl -SL https://github.com/docker/compose/releases/download/v2.2.3/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose
              chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose"

      
              


      end
  
  
   end


end