## 2 x VM-Series (3 NIC) with Public & Internal Load Balancers (Standard SKU)

<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/azure-arm-mclimans/standard_deployments/v1/images/2fw_3nic_avset_intlb_extlb.png">
</p>
transit_1fw_3nic_avset_intlb_extlb_2spokes
### Overview
This template deploys the following:
* 1 x VM-Series firewalls
    * 3 x Interfaces
        * management: `<fw_name>-nic0`
        * dataplane1: `<fw_name>-nic1`
        * dataplane2: `<fw_name>-nic2`
* 3 x VNETs
    * spoke1-vnet 172.17.0.0/16
    * spoke2-vnet 192.168.0.0/16
    * vmseries-vnet 10.0.0.0/16
* VMs
    * spoke1-ubuntu-vm (172.17.0.4)
    * spoke2-ubuntu-vm (192.168.0.4)
    * vmseries-fw-vm1 (10.0.0.4, 10.0.1.5, 10.0.2.5)
* 1 x Standard SKU Public Load Balancer
* 1 x Standard SKU Internal Load Balancer with HA Ports


[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2Fazure-arm-mclimans%2Fdemo_deployments%2Ftransit_1fw_3nic_avset_intlb_extlb_2spokes%2Fv1%2FazureDeploy.json)
