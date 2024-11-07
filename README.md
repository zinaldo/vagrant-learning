## Virtualbox installation

https://forums.fedoraforum.org/showthread.php?320439-F29-VirtualBox-network-adapter-dev-vboxnetctl-missing
https://askubuntu.com/questions/900118/vboxdrv-sh-failed-modprobe-vboxdrv-failed-please-use-dmesg-to-find-out-why

```
  120  sudo apt update
  121  sudo apt install virtualbox-7.1
  122  sudo usermod -aG vboxusers $USER
  123  docker run hello-world
  124  newgrp docker
  125  groups $USER
  126  virtualbox
  127  sudo virtualbox
  128  sudo /sbin/vboxconfig
  129  sudo -i
  130  dmesg|grep 'EFI: Loaded cert'
  131  sudo su
  132  virtualbox
  134  sudo mokutil --disable-validation
  135  /sbin/vboxconfig setup
  136  /sbin/vboxconfig
  137  sudo /sbin/vboxconfig
  138  sudo mokutil --enable-validation
  139  sudo mokutil --sb-state
  140  virtualbox
  141  sudo /sbin/vboxconfig
```

## Vagrant installation
```
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install vagrant
```

## Download last binary
```
sudo mv vagrant /usr/bin/vagrant
sudo apt install libfuse2
```

## Add box
```
vagrant box add ubuntu/trusty64
```

## List boxes
```
vagrant box list
```

## Create vagrant file
```
vagrant init ubuntu/trusty64
```

## Rmove commented lines and empty ones
```
egrep -v "^.*#|^$" Vagrantfile
```

-## SSH into vm
```
vagrant ssh
```

## See number o cores, memory
```
nproc
free -h
```'

## Install plugin
```
vagrant plugin install vagrant-disksize
```

## Lifecycle commands
```
vagrant status
vagrant halt / up (reload)
vagrant suspend / resume
vagrant destroy [-f]
vagrant upload file /home/vagrant/file
```