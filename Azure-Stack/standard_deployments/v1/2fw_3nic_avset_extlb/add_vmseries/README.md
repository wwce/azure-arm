## Add 1 x VM-Series (3 NIC) to existing Public Load Balancer's Backend Pool
<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/azure-arm-mclimans/standard_deployments/v1/images/2fw_3nic_avset_intlb_extlb.png">
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
    * (Optional) Accelerated Networking
    * (Optional) [Bootstrap Capable](https://docs.paloaltonetworks.com/vm-series/8-1/vm-series-deployment/bootstrap-the-vm-series-firewall/bootstrap-the-vm-series-firewall-in-azure)
    * (Optional) Public IPs for interfaces:
        * management: `<fw_name>-nic0-pip`
        * dataplane1: `<fw_name>-nic1-pip`
* 2 x Network Security Groups
    *  management: `<fw_name>-mgmt`
    *  dataplane: `<fw_name>-data`
