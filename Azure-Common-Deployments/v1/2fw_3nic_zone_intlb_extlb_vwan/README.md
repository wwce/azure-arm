## 2 x VM-Series (Zones 3 NIC) with Public & Internal Load Balancers

## Overview
This build includes 3 templates to deploy different resources for securing egress traffic from vWAN Hub Connections through a pair of VM-Series firewalls.
<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/Azure-Common-Deployments/v1/images/2fw_3nic_zone_intlb_extlb_vwan.png">
</p>

## Part 1: Create Virtual WAN / Hub / Hub VPN Gateway
This part creates a Virtual WAN, Virtual Hub, and Virtual Hub's VPN Gateway. 

**Run Time:** ~ *45 Minutes*
</br>
[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Common-Deployments%2Fv1%2F2fw_3nic_zone_intlb_extlb_vwan%2Fpart1_vwan.json)

## Part 2: Create Security VNET with VM-Series
This part deploys a VNET with 4 subnets (mgmt, untrust, trust, GatewaySubnet) and 2 x VM-Series firewalls.  The GatewaySubnet hosts a Virtual Network Gateway that connects to the Virtual Hub's VPN Gateway.  A route table(GatewaySubnet-RTB) is assigned to the GatewaySubnet to direct traffic from Virtual WAN to the VM-Series internal load balancer.

Before launching the template, perform the following:
1. Download the Hub's VPN Gateway Configuration file from Part 1.
2. Copy the values: **IpAddresses/Instance0**, **BgpPeeringAddresses/Instance0**, & **PSK** 
3. Paste the values into the template fields: **Hub Peer Address**, **Hub BGP Address**, & **Hub Shared Key**.

<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/Azure-Common-Deployments/v1/images/2fw_3nic_zone_intlb_extlb_vwan_vpn_config.png">
</p>

**Run Time:** ~ *45 Minutes*
</br>
[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Common-Deployments%2Fv1%2F2fw_3nic_zone_intlb_extlb_vwan%2Fpart2_security.json)

## Part 3: Connect Security VNET's Virtual Network Gateway to Azure Virtual WAN
1. Open the Local Network Gateway and change the ASN from 65510 to 65515.
2. Open the Virtual Netowrk Gateway, click Properties, and copy the Public IP Address, BGP IP Address, & BGP ASN.
3. Open the Virtual Hub's VPN Connection page and paste the values from Step 2.

It may take up to 10 minutes for the connection to appear as "Connected".

## Part 4: Create Hub Spoke VNET
**Run Time:** *15 Minutes*
</br>
</br>
[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Common-Deployments%2Fv1%2F2fw_3nic_zone_intlb_extlb_vwan%2Fpart3_spoke.json)

