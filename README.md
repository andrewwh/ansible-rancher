# Rancher mini-cluster with Ansible and Vagrant
Create a simple rancher 2.0 cluster using Ansible (local) with Vagrant. Servers are CentOS 7.5.

> Warning: Work in progress

## Pre-requisites
- Vagrant
- Virtualbox

Best to use a Linux box, but you can try it on other another OS.

## Provisioning
To create a server and work cluster:
```
vagrant up
```

## Server
Open the [web console](https://192.168.168.100) and login using as user *admin* with password *rancher*