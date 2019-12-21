# RancherOS Configuration
RancherOS configuration is defined by cloud-config.yml file. Instructions defined below on the setup process of RancherOS

## Set Rancher Password 
Booting from Rancher, set a password so you can copy the config file
over to the server 

```
sudo passwd rancher
```

## Create cloud-config.yaml file 
A cloud-config.yml file is required to begin setup and installation,
the cloud config contains the public key needed to ssh into the server
post-install 

```
#cloud-config
ssh_authorized_keys:
  - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDDnHYw09JRd3AhKSF7I1Mq3sfHGsKTukHK3H+7YxM9U1g2FNqdrG9rH7aE9EgkCBtJ5XYP0RucwTwn2l/Suaqbf714Q7aDUGM/wt+R3/nquywuUThNw70PAIr/035si6z89HLvxwhtUyoRrDrl3E6fGnLUXNsZKzYOolYEbdgSF3lFyY3uNLoBqlOe+uydGz4Sas7TBKRSJWceQ+QwwzbNMWio23ey/64m+O/GqE3rWWyCH5DtBiHjosZvfzEJezAokR5Niy+FFhaQWaalpmTLG3qmMa5jx8DRKSo0ZwDwAwzjYjjIfyxNdUHDxiZQGDn9CF3r057FCtGsfRan8ixoWS2cFJME05O7sGxkSiolStiCMCkg380gO2jVlTMHrbK/tVD47vy+vzug7hPKa5Rj5ETdg0upvCj6VoctVzyTQAxW47Js94vr7YuDrSx4Sk6OiZh+4xjQecuXrW6E/C01Yaxpjl/yIK8KZ01pCwAFoX0+UutmS4sUf+oiftUrFtE= dev@dev-server
```

More paramters can be added into the cloud-config file, refer to [Cloudinit] (https://cloudinit.readthedocs.io/en/latest/topics/examples.html).

## Copy cloud-config file to Rancher
Use ros install to install the iso to disk and use parameter -d to define the disk 

```
sudo ros install -c cloud-config.yml -d /dev/sda
```

