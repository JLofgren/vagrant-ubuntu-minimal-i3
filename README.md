# README #

Vagrant config to build a minimal Ubuntu VM with i3wm in VirtualBox. This is
based on the image ubuntu/xenial64:
https://app.vagrantup.com/ubuntu/boxes/xenial64


## How to Build in Windows ##

* VirtualBox 5.2.4
* Install Windows subsystem for Linux (WSL) and Ansible 2.4.0 therein (
  https://www.jeffgeerling.com/blog/2017/using-ansible-through-windows-10s-subsystem-linux):
* Install Vagrant in WSL using this method: https://www.vagrantup.com/docs/other/wsl.html  Note: export VAGRANT_WSL_ENABLE_WINDOWS_ACCESS="1"

Keep your VirtualBox and guest additions in sync using a vagrant plugin
(https://coderwall.com/p/mvf0aq/vagrant-auto-update-virtualbox-guest-additions):

    vagrant plugin install vagrant-vbguest

To enable automated reload during provisioning:

    vagrant plugin install vagrant-reload

To get GUI programs from WSL:

* Install Xming server in windows and start it
* In WSL .bashrc, export DISPLAY=:0.0

Sublime text in WSL
(https://www.lambrospetrou.com/articles/windows-linux-subsystem-editor-setup/):

    wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
    echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
    sudo apt-get update && sudo apt-get install sublime-text
    subl


## Process ##

    vagrant up

Wait while everything loads. If you have the vagrant-vbguest plugin, you may
need to reload a couple of times to get everything updated.

    vagrant reload
    vagrant reload

In order to login in lightdm window, you first need to select i3 in the settings
menu in the upper right.


## TODO ##

* ?


## Reference ##

* https://ubuntuforums.org/showthread.php?t=2361552
* http://sobo.red/CentOS-7-i3wm-Quickstart/
* https://copr.fedorainfracloud.org/coprs/admiralnemo/i3wm-el7/
