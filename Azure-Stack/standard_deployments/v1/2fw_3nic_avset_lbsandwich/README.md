## 2 x VM-Series (3 NIC) with Public Load Balancer (Basic SKU) and 2 x Ubuntu servers

<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/Azure-Stack/standard_deployments/v1/images/2fw_3nic_avset_lbsandwich.png">
</p>

### Overview
This template deploys the following into a new or existing VNET with 3 subnets:
* 2 x VM-Series firewalls
    * 3 x Interfaces
        * management: `<fw_name>-nic0`
        * dataplane1: `<fw_name>-nic1`
        * dataplane2: `<fw_name>-nic2`
    * Managed Disks
    * BYOL License (Only)
    * (Future) [Bootstrapping via VHD attachment]
    * (Optional) Public IPs for interfaces:
        * management: `<fw_name>-nic0-pip`
        * dataplane1: `<fw_name>-nic1-pip`
* 2 x Network Security Groups
    *  management: `<nsg_name>-mgmt`
    *  dataplane: `<nsg_name>-data`
* 2 x Availability Set
* 2 x Ubuntu servers
* 1 x Basic SKU Public Load Balancer (Public)
    *  Backend Pool: `<fw1_name>-nic1` & `<fw2_name>-nic1`
* 1 x Basic SKU Public Load Balancer (Private)
    *  Backend Pool: `<server_name>-nic1` & `<server_name>-nic1`

### Important Considerations

#### VNET Considerations
By default, the template will use the deployment resource group as the location of the VNET.  If the VNET is in a different resource group, the resource group must be specified at deployment time. If deploying a **new** VNET into a **different** resource group, the resource group **must exist** before deployment.

#### Template Modifications
Everything resource in the template is built strictly with variables.  The variables are defined based on the parameters values entered at deployment.  If you need to modify the template, most modifications can be done directly in the variable and parameter section without modifying the resource configuration.  

#### First Deployment
Most deployment failures are due to conflicts with existing resources.  If this is your first time running the template, it is recommended to launch the template into a **new** resource group.

 
 If deploying with the included configuration file, the default credentials are:
 - Username: paloalto
 - Password: PaloAlt0!123!!
