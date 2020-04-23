## 2 x VM-Series in Zones (3 NIC) with Public & Internal Load Balancers

<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/Azure-Common-Deployments/v1/images/2fw_3nic_zone_intlb_extlb.png">
</p>

### Overview
This template deploys the following into a new or existing VNET with 4 subnets:
* 2 x VM-Series firewalls
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
    *  management: `<nsg_name>-mgmt`
    *  dataplane: `<nsg_name>-data`
* 1 x Standard SKU Public Load Balancer
    *  Backend Pool: `<fw1_name>-nic1` & `<fw2_name>-nic1`
* 1 x Standard SKU Internal Load Balancer with HA Ports
    *  Backend Pool: `<fw1_name>-nic2` & `<fw2_name>-nic2`



#### Part 1: Create Virtual WAN / Hub / Hub VPN Gateway
**Run Time: 1 Hour**
If you do not have a Virtual WAN, or you want to demo in a greenfield environment, run this template to create a Virtual WAN, the Virtual WAN Hub, and the Hub's VPN Gateway.

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Common-Deployments%2Fv1%2F2fw_3nic_zone_intlb_extlb_vwan%2Fpart1_vwan.json)

#### Part 2: Create Transit VNET with Load Balanced VM-Series
**Run Time: 40 Minutes**
This part deploys a Transit VNET with 4 subnets: mgmt, untrust, trust, and GatewaySubnet.  2 x VM-Series firewalls are deployed with an interface in the mgmt, untrust, and trust subnets.  The GatewaySubnet will have a route table assigned to handle traffic from the vWAN Hub.  

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Common-Deployments%2Fv1%2F2fw_3nic_zone_intlb_extlb_vwan%2Fpart2_transit.json)

#### Part 3: Create Hub Spoke VNET
**Run Time: 10 Minutes**

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Common-Deployments%2Fv1%2F2fw_3nic_zone_intlb_extlb_vwan%2Fpart3_spoke.json)

### Important Considerations

#### VNET Considerations
By default, the template will use the deployment resource group as the location of the VNET.  If the VNET is in a different resource group, the resource group must be specified at deployment time. If deploying a **new** VNET into a **different** resource group, the resource group **must exist** before deployment.

#### Template Modifications
Everything resource in the template is built strictly with variables.  The variables are defined based on the parameters values entered at deployment.  If you need to modify the template, most modifications can be done directly in the variable and parameter section without modifying the resource configuration.  

#### First Deployment
Most deployment failures are due to conflicts with existing resources.  If this is your first time running the template, it is recommended to launch the template into a **new** resource group.  If you cannot deploy to a new resource group, it is highly recommended to use the `(opt.) Append String To Resources` parameter to append a string to all newly created resources.  This will avoid potential naming conflicts among any existing resources.
