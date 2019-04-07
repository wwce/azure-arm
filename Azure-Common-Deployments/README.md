# Azure Common Deployment Templates

## Version Overview (v1)

**Author: mmclimans@paloaltonetworks.com**

**Date: 04/01/19**

The purpose of the of the ARM templates is to cover the most frequently used deployments for the VM-Series in Microsoft Azure.  The templates can be deployed in a manner to meet Palo Alto Networks Azure Reference Architectures and/or be deployed to meet specific deployment requirements. 

More information on the Palo Alto Networks supported Azure deployments can be found [here](https://live.paloaltonetworks.com/t5/Microsoft-Azure/ct-p/Azure).

* All templates in this repository use:
* Manage Disks for VM-Series Virtual Machines
* Standard SKU Load Balancers & Public Addresses
* Selectable PAN-OS Version
* Accelerated Networking (optional)
* Bootstrapping (optional)
* Managed Scale (for load balancing templates only).
* Aligned SKU Availability Set (optional)
* Number of VM-Series (1-2)
* Number of VM-Series interfaces (1-3)

## Overview


## Support Policy
This solution is released under an as-is, best effort, support policy. These scripts should be seen as community supported and Palo Alto Networks will contribute our expertise as and when possible. We do not provide technical support or help in using or troubleshooting the components of the project through our normal support options such as Palo Alto Networks support teams, or ASC (Authorized Support Centers) partners and backline support options. The underlying product used (the VM-Series firewall) by the scripts or templates are still supported, but the support is only for the product functionality and not for help in deploying or using the template or script itself.

