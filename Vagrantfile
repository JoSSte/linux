# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "kalilinux/rolling"

  config.vm.provider :virtualbox do |v|
    v.gui = true
    v.memory = 8192
    v.customize ["modifyvm", :id, "--vram", "127"]
  end

  # to make synced folder works.
  config.vm.synced_folder ".", "/home/vagrant/sharedWithHost", type: "virtualbox"

  
  # set keyboard layout to danish
  config.vm.provision :shell, inline: "sudo setxkbmap -layout dk"
  
  # install gobuster
  config.vm.provision :shell, inline: "sudo apt-get install gobuster -y"

  # install flameshot for screenshot documentation
  config.vm.provision :shell, inline: "sudo apt-get install flameshot -y"

  # Restart
  #config.vm.provision :shell, inline: "sudo shutdown -r now"
end