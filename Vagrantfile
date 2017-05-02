Vagrant.configure("2") do |config|
 #Cent OS 6.5
 config.vm.box = "puphpet/centos65-x64"
 
 #execucao do script via ssh
 config.ssh.pty = true

 #Private network
 config.vm.network "private_network", ip: "192.168.33.11"
 
 #Instalação Node, sails e grunt
 config.vm.provision "shell",
 path: "./scripts/nodejs.sh",
 privileged: true
 
 #Instalação MySQL
 config.vm.provision "shell",
 path: "./scripts/mongodb.sh",
 privileged: true

 #Setup aplicacoes
 config.vm.provision "shell",
 path: "./scripts/setup.sh",
 run: "always" 

 config.vm.network :forwarded_port, host: 27018, guest: 27018 #MongoDB
 config.vm.network :forwarded_port, host: 1337, guest: 1337 #Sails ( Node )
 config.vm.network :forwarded_port, guest: 80, host: 8080 #default

end