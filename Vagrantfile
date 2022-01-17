Vagrant.configure("2") do |config|
  config.vm.box = "generic/debian11"
  config.vm.hostname = "jenkins"
  config.vm.provider "virtualbox" do |v|
    # v.gui = true
    v.name = "m08uf4pr4"
    v.memory = 2048
    v.cpus = 2
    v.customize ['modifyvm', :id, '--clipboard', 'bidirectional']     
  end
  
  config.vm.network "forwarded_port", guest: 8080, host: 8080
         
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -y
    sudo apt-get upgrade -y
    sudo apt-get install -y net-tools
    sudo apt-get install -y aptitude      
  SHELL

end
