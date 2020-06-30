# Azure-Shared-Firewall-Ref-Architecture
Deploy a shared firewall infrastructure described in the Paloaltonetworks Azure Reference Architecture Guide


![alt text](https://raw.githubusercontent.com/jharris10/shared-fw-ref-architecture/master/Architecture-Diagram.png)

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjharris10%2Fshared-fw-ref-architecture%2Fmaster%2FazureDeploy.json)

This template automates deployment of firewall LB sandwich environment for Egress Security.
It includes following components:

- One Internal Load Balancer (LB-Egress) - "Standard SKU"
- One External TCP Load Balancer (LB-Ingress) -"Standard - SKU"
- Two Palo Alto Networks Firewalls
- One Ubuntu Server to test outbound traffic
- Multiple Subnets and UDRs to support the traffic flow

 The template allows selection of:
 - New or Existing VNET
 - Bootstraping
 - BYOL or PAYG Licensing
 and creates all the infrastructure and appropriate UDRs.

 For information on how to bootstrap the VM-Series firewall running PAN-OS 8.1 and up in Azure see [Bootstrap Instructions](https://www.paloaltonetworks.com/documentation/81/virtualization/virtualization/bootstrap-the-vm-series-firewall/bootstrap-the-vm-series-firewall-in-azure#idd51f75b8-e579-44d6-a809-2fafcfe4b3b6)

 
 If bootstraping with default configuration file is used default credentials are:
 - Username: paloalto
 - Password: PaloAlt0!123!!
