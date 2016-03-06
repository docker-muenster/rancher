# rancher
Resources about Rancher

## Tips and tricks

## Changing cloud config

    $ sudo ros config merge
    <config options in YAML format..>
    <CTRL-D>

## Loading new remote cloud config onto server

    wget -O - https://raw.githubusercontent.com/docker-muenster/rancher/master/cloud-config/cloud-config.yml | sudo ros config merge

### Reloading networking configuration without reboot

First, change the network configuration in the cloud config (see above on how do do that).

Then apply the new cloud config on the system:

    $ sudo cloud-init -execute
    
For the new network configuration to take effect, you have to restart the network service:

    $ sudo ros service restart network
