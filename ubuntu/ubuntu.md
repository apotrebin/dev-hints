
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

#### Useful apps
> https://github.com/oguzhaninan/Stacer - cleaner and system monitor
> https://kdenlive.org - video editor
> https://launchpad.net/~sylvain-pineau/+archive/ubuntu/kazam - screen recorder 
> https://flameshot.js.org   https://github.com/flameshot-org/flameshot/releases - screenshoter
> https://deluge-torrent.org - torrent client
