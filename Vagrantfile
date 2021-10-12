
Vagrant.configure("2") do |config|
   config.vm.box = "hashicorp/bionic64"
   config.vm.box_check_update = false
   config.vm.network "forwarded_port", guest: 3306, host: 3306
   config.vm.provision "shell", inline: <<-SHELL
     apt-get update
    apt-get install -y mysql-server
    sed -i "s/.*bind-address.*/bind-address = 0.0.0.0/" /etc/mysql/my.cnf
   SHELL
end
