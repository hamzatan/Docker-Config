# Configuration for Bridge Networking 
Configuration required to setup bridge networking for KVM, alternative to NAT using NETPLAN 

## Install bridge-utils
Bridge-utils is required to run NetPlan, install via command below
```
sudo apt-get install bridge-utils -y
```

## Edit the current netplan file
Change directory into "/etc/netplan" and modify the cloud-init.yml file, 

Make a backup of the Cloud-Init file 
```
sudo cp 50-cloud-init.yaml 50-cloud-init.yaml.bak 
````

  
