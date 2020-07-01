## Add 1 x VM-Series (3 NIC) to existing Public Load Balancer's Backend Pool
<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/Azure-Stack/standard_deployments/v1/images/2fw_3nic_avset_extlb.png">
</p>

### Overview
This template deploys the following into a new or existing VNET with 4 subnets:
* 1 x VM-Series firewalls
    * 3 x Interfaces
        * management: `<fw_name>-nic0`
        * dataplane1: `<fw_name>-nic1`
        * dataplane2: `<fw_name>-nic2`
    * Managed Disks
    * BYOL/Bundle1/Bundle2 License
    * BYOL License (Only)
    * (Future) [Bootstrapping via VHD attachment]
    * (Optional) Public IPs for interfaces:
        * management: `<fw_name>-nic0-pip`
        * dataplane1: `<fw_name>-nic1-pip`
* 2 x Network Security Groups
    *  management: `<fw_name>-mgmt`
    *  dataplane: `<fw_name>-data`
