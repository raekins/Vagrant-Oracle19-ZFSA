# Vagrant Oracle 19c ZFS Appliance VM
Fully automatted Vagrant Ansible Oracle 19c build using ZFS NFSv4.1 and dNFS 

Pre-requistes
- VirtualBox
- ZFS Appliance VM Simulator
- Vagrant

For details on how to install and configure the ZFS Appliance for NFS and iSCSI block volumes read the following:
- ZFS Appliance VM Installation on VirtualBox https://ronekins.com/2021/02/02/getting-started-with-the-oracle-zfs-storage-appliance-simulator-on-virtualbox/ 
- Setting up NFSv4.1 and dNFS https://ronekins.com/2022/03/15/oracle-19c-database-nfsv4-1-oracle-direct-nfs-dnfs-and-the-oracle-zfs-storage-appliance-simulator/
- Setting up iSCSI block Luns https://ronekins.com/2022/03/30/how-to-configure-the-oracle-zfs-storage-appliance-vm-simulator-for-iscsi-block-storage/ 

### Preperation
Pull this repo
```
% git pull https://github.com/raekins/Vagrant-Oracle19-ZFSA.git
```
Download and copy `oracle-database-ee-19c-1.0-1.x86_64.rpm` into ../vagrant/software/

### Vagarant Virtual Machine Usage
The Vagrant file pull the latest Oracle Linux box from https://yum.oracle.com/boxes/oraclelinux/latest/ol7-latest.box for example:
```
% vagrant box list
ol7-latest                (virtualbox, 0)
```
To start Oracle Liunx 7.9 database Virtual Machine type:
```
$ vagrant up
```
To logon to the Virtual Machine
```
$ vagrant ssh
```
To delete and tidy up the Virtual Machine
```
$ vagrant destroy
    default: Are you sure you want to destroy the 'default' VM? [y/N] 
```
### Database Management
As the vagrant user sudo to `root` or `oracle`, for example
```
$ sudo su - oracle
```
The Ansible playbook creates a DBCA silent installation script, this can be run as-is or ammended as required.
```
dbca_silent_create.sh
```
There is also a DBCA silent delete script.
```
dbca_silent_delete.sh
```
### Authors
Ron Ekins, Principal Solutions Architect, Office of the CTO at Pure Storage

Oracle ACE Director

@ronekins
