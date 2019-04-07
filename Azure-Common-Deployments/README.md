# Azure Common Deployment Templates

## About
Author:mmclimans@paloaltonetworks.com</br>
Date: 04/01/19

The purpose of the of the ARM templates is to cover the most frequently used deployments for the VM-Series in Microsoft Azure.  The templates can be deployed in a manner to meet Palo Alto Networks Azure Reference Architectures and/or be deployed to meet specific deployment requirements.  More information on the Palo Alto Networks supported Azure deployments can be found [here](https://live.paloaltonetworks.com/t5/Microsoft-Azure/ct-p/Azure).

## v1 - Overview
Below is a high level overview of Common ARM Deployment templates (v1).
#### VNET Settings
* New or Existing VNET
   * Subnets (1-4)
      * management-subnet
      * dataplane1-subnet (optional)
      * dataplane2-subnet (optional)
      * loadbalancer-subnet (optional)
* The VNET Resource Group can be different than main deployments, however the VNET Resource Group must exist before deployment.
#### Virtual Machine Settings
* VM-Series VM (1-2)
* Managed Disk
* Interfaces (1-3)
   * management (public address optional)
   * dataplane1 (public address optional)
   * dataplane2 
* New/Existing Availability Set (aligned SKU)
#### VM-Series PAN-OS Settings
* Selectable PAN-OS Version
* Selectable PAN-OS License (BYOL/BUNDLE1/BUNDLE2)
* Accelerated Networking (optional)
* Bootstrapping (optional)
#### Load Balancer Settings
* Internal Load Balancer (standard SKU)
   * Configured with HA Ports
* Public Load Balancer (standard SKU)
   * Configured with 1 frontend address and various load balancing ports (defined at deployment)

## Support Policy
This solution is released under an as-is, best effort, support policy. These scripts should be seen as community supported and Palo Alto Networks will contribute our expertise as and when possible. We do not provide technical support or help in using or troubleshooting the components of the project through our normal support options such as Palo Alto Networks support teams, or ASC (Authorized Support Centers) partners and backline support options. The underlying product used (the VM-Series firewall) by the scripts or templates are still supported, but the support is only for the product functionality and not for help in deploying or using the template or script itself.

