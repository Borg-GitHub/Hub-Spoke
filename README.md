# Hub-Spoke

This automation builds a hub-spoke topology in Azure. The hub virtual network acts as a central point of connectivity to many spoke virtual networks. The hub can also be used as the connectivity point to your on-premises networks. The spoke virtual networks peer with the hub and can be used to isolate workloads.

The benefits of using a hub and spoke configuration include cost savings, overcoming subscription limits, and workload isolation.

<br />
<br />

<img src=hub-spoke.png>

<br />
<br />



# Architecture
The architecture consists of the following components.

Hub virtual network: The hub virtual network is the central point of connectivity to your on-premises network. It's a place to host services that can be consumed by the different workloads hosted in the spoke virtual networks.

Spoke virtual networks: Spoke virtual networks are used to isolate workloads in their own virtual networks, managed separately from other spokes. Each workload might include multiple tiers, with multiple subnets connected through Azure load balancers.

Virtual network peering: Two virtual networks can be connected using a peering connection. Peering connections are non-transitive, low latency connections between virtual networks. Once peered, the virtual networks exchange traffic by using the Azure backbone without the need for a router.

Bastion Host: Azure Bastion lets you securely connect to a virtual machine using your browser and the Azure portal. An Azure Bastion host is deployed inside an Azure Virtual Network and can access virtual machines in the VNet, or virtual machines in peered VNets.

Azure Firewall: Azure Firewall is a managed firewall as a service. The Firewall instance is placed in its own subnet.

VPN virtual network gateway or ExpressRoute gateway. The virtual network gateway enables the virtual network to connect to the VPN device, or ExpressRoute circuit, used for connectivity with your on-premises network. For more information, see Connect an on-premises network to a Microsoft Azure virtual network.

VPN device. A device or service that provides external connectivity to the on-premises network. The VPN device may be a hardware device or a software solution such as the Routing and Remote Access Service (RRAS) in Windows Server 2012. For more information, see About VPN devices for Site-to-Site VPN Gateway connections.

<br />


## Installation

Use the Deploy to Azure button below. 

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FBorg-GitHub%2FHub-Spoke%2Fmain%2FTemplates%2Ftemplate.json)

**The template allows for the following parameters**
* adminUserName  - The username for the local administrators of the two virtual machines provisioned. 
* adminPassword - 
* windowsVMCount -
* linuxVMCount -
* vmSize -
* deployVpnGateway -
* hubNetwork -
* spokeNetwork -
* spokeNetworkTwo -
* vpnGateway -
* bastionHost -
* azureFirewall -
* workbookDisplayName -
* workbookId -
* location -






