Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.box_check_update = false
  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "forwarded_port", guest: 443, host: 443
  config.vm.synced_folder ".", "/vagrant"
  config.ssh.username = "vagrant"
  config.ssh.password = "vagrant"
  config.vm.network "private_network", ip: "192.168.33.11"
end

Usar o comando abaixo diretamente no Win10
#set VAGRANT_PREFER_SYSTEM_BIN=0
