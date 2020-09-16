
* sudo apt update && sudo apt dist-upgrade && sudo apt autoremove




> VirtualBox

```
change VirtualBox settings to allow auto-installation from CD 
sudo apt install virtualbox-guest-dkms linux-headers-virtual
install guest cd 
```

#### Keep clean Ubuntu
```
sudo apt-get autoremove
sudo rm -rf ~/.cache/thumbnails/*
du -sh ~/.cache/thumbnails

sudo dpkg --list 'linux-image*'
sudo apt-get remove linux-image-VERSION
or
sudo apt-get autoremove --purge


sudo du -sh /var/cache/apt
sudo apt-get clean
```
