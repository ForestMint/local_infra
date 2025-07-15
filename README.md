vagrant up

vagrant ssh

# Install VirtualBox

sudo pacman -Syu virtualbox

sudo pacman -Sy archlinux-keyring
sudo pacman-key --init
sudo pacman-key --populate archlinux
sudo pacman-key --refresh-keys
sudo pacman -Syu

sudo pacman -Syu virtualbox

sudo pacman -Syu virtualbox virtualbox-host-dkms linux-headers dkms\
sudo pacman -S virtualbox-host-modules-arch
sudo modprobe vboxdrv

sudo pacman -S virtualbox-host-modules-arch
sudo reboot
sudo modprobe vboxdrv

# Install Git

yes Y | sudo pacman -S git

# Install Vagrant

git clone https://aur.archlinux.org/vagrant.git
cd vagrant
makepkg -si

# Clone Jenkins server setup repository

git clone https://github.com/ForestMint/set_up_jenkins.git
