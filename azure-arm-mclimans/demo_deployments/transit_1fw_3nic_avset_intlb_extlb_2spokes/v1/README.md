## 2 x VM-Series (3 NIC) with Public & Internal Load Balancers (Standard SKU)

## Option A: Step 1
Deploy 1 VM-Series firewall with 2 Spoke VNETs. Includes Public and Internal Load Balancer.

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2Fazure-arm-mclimans%2Fdemo_deployments%2Ftransit_1fw_3nic_avset_intlb_extlb_2spokes%2Fv1%2FoptA_step1.azureDeploy.json)
<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/azure-arm-mclimans/demo_deployments/transit_1fw_3nic_avset_intlb_extlb_2spokes/v1/images/optA_step1.png">
</p>

## Option A: Step 2
Add 1 VM-Series firewall to the backend pools of the load balancers created in Step 1.  Step 1 must be deployed prior to launching Step 2.

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwwce%2Fazure-arm%2Fmaster%2Fazure-arm-mclimans%2Fdemo_deployments%2Ftransit_1fw_3nic_avset_intlb_extlb_2spokes%2Fv1%2FoptA_step2.azureDeploy.json)
<p align="center">
<img src="https://raw.githubusercontent.com/wwce/azure-arm/master/azure-arm-mclimans/demo_deployments/transit_1fw_3nic_avset_intlb_extlb_2spokes/v1/images/optA_step2.png">
</p>
