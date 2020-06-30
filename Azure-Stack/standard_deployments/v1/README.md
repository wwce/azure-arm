# ARM: VM-Series Standard Deployment Templates - Azure Stack Version

All templates in this repository use Manage Disks. Features such as Accelerated Networking, Autoscaling, Standard SKU Load balancers, Application Gateways, etc. are not currently supported in Azure Stack and are perforce omitted from these tempaltes. Additionally, the templates are configured to use the most current API versions supported in Azure Stack as of June 2020:

Resources: 2016-06-01

Network: 2018-11-01

Compute: 2017-12-01

## Support Policy

pglynn@paloaltonetworks.com if you spot any issues or see areas for improvement.

These ARM templates are released under an as-is, best effort, support policy. These scripts should be seen as community supported and Palo Alto Networks will contribute our expertise as and when possible. We do not provide technical support or help in using or troubleshooting the components of the project through our normal support options such as Palo Alto Networks support teams, or ASC (Authorized Support Centers) partners and backline support options. The underlying product used (the VM-Series firewall) by the scripts or templates are still be supported, but the support is only for the product functionality and not for help in deploying or using the template or script itself. Unless explicitly tagged, all projects or work posted in our GitHub repository (at https://github.com/PaloAltoNetworks) or sites other than our official Downloads page on https://support.paloaltonetworks.com are provided under the best effort policy.



---

### [2fw_3nic_avset_lbsandwich](https://github.com/wwce/azure-arm/tree/master/azure-stack/standard_deployments/v1/2fw_3nic_avset_lbsandwich)
Deploy 2 x VM-Series (3 NIC) with External Load Balancer (Basic SKU) and 2 x Ubuntu hosts to act as servers
<img style="float: left;" src="https://github.com/wwce/azure-arm/raw/master/Azure-Stack/standard_deployments/v1/images/2fw_3nic_avset_lbsandwich.png" alt="drawing" width="500"/>

---

### [2fw_3nic_avset_extlb](https://github.com/wwce/azure-arm/tree/master/azure-stack/standard_deployments/v1/2fw_3nic_avset_extlb)
Deploy 2 x VM-Series (3 NIC) with Public Load Balancer (Basic SKU)
<img style="float: left;" src="https://github.com/wwce/azure-arm/raw/master/Azure-Stack/standard_deployments/v1/images/2fw_3nic_avset_extlb.png" 
alt="drawing" width="500"/>

---

### [2fw_3nic_avset](https://github.com/wwce/azure-arm/tree/master/azure-stack/standard_deployments/v1/2fw_3nic_avset)
Deploy 2 x VM-Series (3 NIC)
</br>
<img style="float: left;" src="https://github.com/wwce/azure-arm/raw/master/Azure-Stack/standard_deployments/v1/images/2fw_3nic_avset.png" alt="drawing" width="400"/>

---

### [2fw_2nic_avset](https://github.com/wwce/azure-arm/tree/master/azure-stack/standard_deployments/v1/2fw_2nic_avset)
Deploy 2 x VM-Series (2 NIC)
</br>
<img style="float: left;" src="https://github.com/wwce/azure-arm/raw/master/Azure-Stack/standard_deployments/v1/images/2fw_2nic_avset.png" alt="drawing" width="400"/>

---

### [2fw_1nic_avset](https://github.com/wwce/azure-arm/tree/master/azure-stack/standard_deployments/v1/2fw_1nic_avset)
Deploy 2 x VM-Series (1 NIC)
</br>
<img style="float: left;" src="https://github.com/wwce/azure-arm/raw/master/Azure-Stack/standard_deployments/v1/images/2fw_1nic_avset.png" alt="drawing" width="400"/>

---

### [1fw_3nic_avset](https://github.com/wwce/azure-arm/tree/master/azure-stack/standard_deployments/v1/1fw_3nic_avset)
Deploy 1 x VM-Series (3 NIC)
</br>
<img style="float: left;" src="https://github.com/wwce/azure-arm/raw/master/Azure-Stack/standard_deployments/v1/images/1fw_3nic_avset.png" alt="drawing" width="400"/>

---

### [1fw_2nic_avset](https://github.com/wwce/azure-arm/tree/master/azure-stack/standard_deployments/v1/1fw_2nic_avset)
Deploy 1 x VM-Series (2 NIC)
</br>
<img style="float: left;" src="https://github.com/wwce/azure-arm/raw/master/Azure-Stack/standard_deployments/v1/images/1fw_2nic_avset.png" alt="drawing" width="400"/>

---

### [1fw_1nic_avset](https://github.com/wwce/azure-arm/tree/master/azure-stack/standard_deployments/v1/1fw_1nic_avset)
Deploy 1 x VM-Series (1 NIC)
</br>
<img style="float: left;" src="https://github.com/wwce/azure-arm/raw/master/Azure-Stack/standard_deployments/v1/images/1fw_1nic_avset.png" alt="drawing" width="400"/>
