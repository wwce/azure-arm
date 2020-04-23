## 2 x VM-Series (Zones 3 NIC) with Public & Internal Load Balancers

## Overview
This build includes 3 templates to deploy different resources for securing egress traffic from vWAN Hub Connections through a pair of VM-Series firewalls.
<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/Azure-Common-Deployments/v1/images/2fw_3nic_zone_intlb_extlb.png">
</p>

## Part 1: Create Virtual WAN / Hub / Hub VPN Gateway
**Run Time:** *1 Hour*
</br>
</br>
If you do not have a Virtual WAN, or you want to demo in a greenfield environment, run this template to create a Virtual WAN, the Virtual WAN Hub, and the Hub's VPN Gateway.

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Common-Deployments%2Fv1%2F2fw_3nic_zone_intlb_extlb_vwan%2Fpart1_vwan.json)

After the deployment finishes, perform the following:


## Part 2: Create Transit VNET with Load Balanced VM-Series
**Run Time:** *35 Minutes*
</br>
</br>
This part deploys a Transit VNET with 4 subnets: mgmt, untrust, trust, and GatewaySubnet.  2 x VM-Series firewalls are deployed with an interface in the mgmt, untrust, and trust subnets.  The GatewaySubnet will have a route table assigned to handle traffic from the vWAN Hub.  

Connect the Transit VNET's Virtual Network Gateway to the vWAN Hub.
* Copy the Virtual Network Gateway's Public IP address under Properties. 
* Go to the Hub's VPN settings and change the remote sites IP to match the Transit Virtual Network Gateway's IP.
* Download Virtual Hub's VPN Configuration File
* Open Transit VNET's Local Network Gateway
    * Set the BGP ASN to 65515.  This is the ASN that Virtual WAN uses.
    * The Local Network Gateway's IP address should be the Instance0 value from the VPN configuration file in Part 1.


[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Common-Deployments%2Fv1%2F2fw_3nic_zone_intlb_extlb_vwan%2Fpart2_transit.json)

## Part 3: Create Hub Spoke VNET
**Run Time:** *15 Minutes*
</br>
</br>
[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Common-Deployments%2Fv1%2F2fw_3nic_zone_intlb_extlb_vwan%2Fpart3_spoke.json)

