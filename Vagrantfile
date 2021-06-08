# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "ubuntu/focal64"

  config.vm.provider :virtualbox do |v|
    v.gui = true
    v.memory = 8192
    v.customize ["modifyvm", :id, "--vram", "127"]
  end

  # to make synced folder works.
  config.vm.synced_folder ".", "/home/vagrant/sharedWithHost", type: "virtualbox"

  ## Add Google Chrome repository
  #config.vm.provision :shell, inline: "wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub|sudo apt-key add -"
  #config.vm.provision :shell, inline: "sudo sh -c 'echo \"deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main\" > /etc/apt/sources.list.d/google.list'"

  # Update repositories
  config.vm.provision :shell, inline: "sudo apt-get update -y"

  # Upgrade installed packages
  config.vm.provision :shell, inline: "sudo apt-get upgrade -y"

  # Add desktop environment
  config.vm.provision :shell, inline: "sudo apt-get install -y --no-install-recommends ubuntu-desktop"
  config.vm.provision :shell, inline: "sudo apt-get install -y --no-install-recommends virtualbox-guest-dkms virtualbox-guest-utils virtualbox-guest-x11"
  
  # Add `vagrant` to Administrator
  config.vm.provision :shell, inline: "sudo usermod -a -G sudo vagrant"

  ## Add Google Chrome
  #config.vm.provision :shell, inline: "sudo apt-get install -y google-chrome-stable"

  # Add Chromium
  config.vm.provision :shell, inline: "sudo apt-get install -y chromium-browser"

  # Add Firefox
  config.vm.provision :shell, inline: "sudo apt-get install -y firefox"

  # get visual studio code
  # https://code.visualstudio.com/docs/setup/linux
  config.vm.provision :shell, inline: "wget https://go.microsoft.com/fwlink/?LinkID=760868 -O code.deb"

  # install 
  config.vm.provision :shell, inline: "sudo apt install ./code.deb"


  # Restart
  config.vm.provision :shell, inline: "sudo shutdown -r now"
end