# Common Azure ARM Templates

## Azure Reference Architecture Templates

The templates in this section allow you to deploy VM Series firewalls set out in the Azure Reference Architecture Guide. 

<https://www.paloaltonetworks.com/resources/whitepapers/intelligent-architectures-azure-reference-architecture>

The design models in this section offer example architectures that secure inbound access to an application in Azure, the communication between private virtual machines and workloads, and the connection to your on-site networks.
The design models primarily differ in how traffic flows are divided amongst VM-Series firewalls while offering you flexibility in the number of firewalls, scale, and operational resiliency. Consider which model best fits your needs and use it as a starting point for your design. The design models in the reference design are the:

* Shared model

In this model, all traffic flows through a single set of firewalls. This model keeps the number of firewalls low for small deployments and proof-of-concepts. However, the technical integration complexity is
high.

[Shared Model ARM Template](https://github.com/wwce/azure-arm/tree/master/Azure-Shared-Firewall-Ref-Architecture-master)


* Scaled model

The model separates inbound traffic flows onto a dedicated set of firewalls while all other traffic flows through a shared firewall set. This design reduces technical integration complexity and increases scale compared to the shared model.

[Scaled Model ARM Template](https://github.com/wwce/azure-arm/tree/master/Azure-Scaled-Firewall-Ref-Architecture-master)


* Dedicated model

Inbound, outbound and east-west, and backhaul traffic are each on dedicated sets of firewalls. This model offers increased operational resiliency and reduces the chances of high bandwidth use from one traffic profile affecting another.
