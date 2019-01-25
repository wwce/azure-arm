# Palo Alto Networks LB Sandwitch for Azure Egress Security

![alt text](https://raw.githubusercontent.com/dstanic-pan/azure-arm/azure-egress-lb-standard-new-existing-vnet-bootstrap/Architecture-Diagram.png)

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdstanic-pan%2Fazure-egress%2Fmaster%2FazureDeploy.json)

This template automates deployment of firewall LB sandwich environment for Egress Security.
It includes following components:

- One Internal Load Balancer (LB-Egress) - "Standard SKU"
- Two Palo Alto Networks Firewalls
- One Ubuntu Server to test outbound traffic
- Multiple Subnets and UDRs to support the traffic flow

 The template allows selection of:
 - New or Existing VNET
 - Bootstraping
 - BYOL or PAYG Licensing
 and creates all the infrastructure and appropriate UDRs.
 
 If bootstraping with default configuration file is used default credentials are:
 - Username: paloalto
 - Password: PaloAlt0!123!!
