vagrant up

vagrant ssh

# Update pacman

sudo pacman -Sy

# Install Git

yes Y | sudo pacman -S git
git --version

# update pacman keys

yes Y | sudo pacman -Sy archlinux-keyring

# Inatall yay

git clone https://aur.archlinux.org/yay.git
cd yay
sudo pacman -S debugedit
sudo pacman -S fakeroot
makepkg -si
yay --version
cd ..
rm -rf yay

# Install vagrant with yay

yay -S vagrant
vagrant --version

# Install Qemu

sudo pacman -Syu qemu-full qemu-img libvirt virt-manager virt-viewer edk2-ovmf dnsmasq swtpm guestfs-tools libosinfo tuned

# Clone Jenkins server setup repository

git clone https://github.com/ForestMint/set_up_jenkins_for_local_infra.git

cd set_up_jenkins






















# the following does not work


sudo pacman -S --needed base-devel git

git clone https://aur.archlinux.org/yay.git

cd yay

makepkg -si


# run THE vm

sudo pacman -Syu --needed libvirt qemu ruby base-devel libxml2 libxslt
vagrant plugin install vagrant-libvirt
vagrant plugin list
sudo vagrant up --provider=libvirt


# Install Qemu

sudo pacman -S qemu virt-manager virt-viewer dnsmasq vde2 bridge-utils openbsd-netcat libvirt
sudo systemctl enable --now libvirtd
sudo usermod -aG libvirt $(whoami)
qemu-system-x86_64 --version

# Install yay

git clone https://aur.archlinux.org/yay.git
sudo ln -sf /run/systemd/resolve/stub-resolv.conf /etc/resolv.conf
export GO111MODULE=on
export GOPROXY=https://goproxy.cn,direct
cd yay
makepkg -i
cd ..
rm -rf yay
yay --version

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

# Install paru

git clone https://aur.archlinux.org/paru.git
cd paru

sudo pacman -S debugedit
sudo pacman -S fakeroot
sudo pacman -S pkg-config
sudo pacman -S openssl

makepkg -si
paru --version
cd ..
rm -rf paru

# Install Vagrant with paru

sudo pacman -Syu

paru -S vagrant

vagrant --version

# Clone Jenkins server setup repository

git clone https://github.com/ForestMint/set_up_jenkins.git

cd set_up_jenkins

sudo vagrant up --provider=libvirt




exit

yes y | vagrant destroy
