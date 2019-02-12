# Azure-Firewall-into-existing-environment

Select the template that matches your requirements

This template was created to support the deployment of a 2 interface Palo Alto Networks firewall into an existing Microsoft Azure environment that has the following items already deployed:
The following are required
                    -Availability Set for the Firewall
                    -VNET - with 2 subnets (Management + Trust)
                    -Resource Group for Firewall

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAdd-new-firewalls-to-existing-deployment%2FAdd-New-Firewall-AzureDeploy-2NIC.json)

This template was created to support the deployment of a 3 interface Palo Alto Networks firewall into an existing Microsoft Azure environment that has the following items already deployed:
The following are required
                    -Availability Set for the Firewall
                    -VNET - with 2 subnets (Management + Untrust + Trust)
                    -Resource Group for Firewall

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAdd-new-firewalls-to-existing-deployment%2FAdd-New-Firewall-AzureDeploy.json)

This template was created to support the deployment of a 4 interface Palo Alto Networks firewall into an existing Microsoft Azure environment that has the following items already deployed:
The following are required
                    -Availability Set for the Firewall
                    -VNET - with 3 subnets
                    -Resource Group for Firewall

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAdd-new-firewalls-to-existing-deployment%2FAdd-New-Firewall-AzureDeploy-4NIC.json)

This template was created to support the deployment of a 3 interface Palo Alto Networks firewall into an existing Microsoft Azure environment that has the following items already deployed but is NOT a member of an availability set:
                    -VNET - with 3 subnets
                    -Resource Group for Firewall

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2FAdd-new-firewalls-to-existing-deployment%2FAdd-New-Firewall-AzureDeploy-no-AS.json)


FEATURES:

- It is possible to choose the version of software the firewall is running. 7.1 or 8.0 (Latest)
- The deployment SKU can also be choosen during deployment.  BYOL, Bundle1 or Bundle2 are the available options.
- Static IP addresses assignment is used for all the firewall interfaces.


The following managed disk types are supported:

                    -Premium_LRS
                    -Standard_LRS

The following VMs are supported:

                    -Standard_D3
                    -Standard_D4
                    -Standard_D3_v2
                    -Standard_D4_v2
                    -Standard_DS3_v2
                    -Standard_DS4_v2

NOTE: Make sure the VMs are supported in the specific Storage Account Type and Azure Region.

After deploying, this firewall can be intetgrated into a load balancer setup via the Azure Portal.

