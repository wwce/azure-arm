# Azure-Dedicated-Firewall-Ref-Architecture
Deploy a Scaled firewall infrastructure described in the Paloaltonetworks Azure Reference Architecture Guide


![alt text](https://raw.githubusercontent.com/wwce/azure-arm/master/Azure-Dedicated-Firewall-Ref-Architecture-master/Documentation/topology.png)

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAzure-Dedicated-Firewall-Ref-Architecture-master%2FazureDeploy.json)

This template automates deployment of 2 pairs of firewalls LB for ingress and egress Security.
It includes following components:

- One Internal Load Balancer (LB-Egress) - "Standard SKU"
- One Internal Load Balancer (LB-VPN) - "Standard SKU"
- One External TCP Load Balancer (LB-Ingress) -"Standard - SKU"
- Three Pairs of Palo Alto Networks Firewalls


 The template allows selection of:
 - New or Existing VNET
 - Bootstraping
 - BYOL or PAYG Licensing
 and creates all the infrastructure and appropriate UDRs.

 For information on how to bootstrap the VM-Series firewall running PAN-OS 8.1 and up in Azure see [Bootstrap Instructions](https://www.paloaltonetworks.com/documentation/81/virtualization/virtualization/bootstrap-the-vm-series-firewall/bootstrap-the-vm-series-firewall-in-azure#idd51f75b8-e579-44d6-a809-2fafcfe4b3b6)

 
 If bootstraping with default configuration file is used default credentials are:
 - Username: paloalto
 - Password: Pal0Alt0123!

