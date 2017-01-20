# README #

one way to use vagrant to create an Islandora 7.x-1.8 virtual machine using VirtualBox setting the Linux distribution at initial startup

# How do I get set up? #

## Dependencies ##
     * install Git, Vagrant 1.9.x, and VirtualBox 5.x

## Deployment Instructions ##
* set environmental variables 
     * defaults are:
          * ISLANDORA_VAGRANT_CPUS  = 2
          * ISLANDORA_VAGRANT_MEMORY = 3048
          * ISLANDORA_VAGRANT_HOSTNAME = islandora
          * ISLANDORA_VAGRANT_OS  = ubuntu/trusty64

* creating virtual machine

```
#!bash
cd [project directory name]
git clone https://github.com/edf/islandora7x-vagrant [optional preferred directory name]
cd  [directory name created from previous command]
vagrant box update *(optional step)*
vagrant up


vagrant ssh
sudo ansible-playbook /vagrant/playbook.yml
```
### Setting Environment Variables ###

#### Linux or Git Bash on Windows ####
```export ISLANDORA_VAGRANT_CPUS="2"```
#### OS X ####
```export ISLANDORA_VAGRANT_CPUS="2"```
#### Windows ####
```set %ISLANDORA_VAGRANT_CPUS%="2"```


# Notes

## Errors

### required for initial run if using CentOS 7



```
#!php
$ vagrant box update
==> default: Box 'geerlingguy/centos7' not installed, can't check for updates
```

substitute the following:
```
vagrant box add geerlingguy/centos7 
vagrant box update
vagrant up
```
