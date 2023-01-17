# 1. Create a Vnet and set up a subnet on the created Vnet

### Virtual network (VNet)

- A virtual network (VNet) in Azure is a representation of your own network in the cloud.
- You can use a VNet to create a secure and isolated network environment in Azure, and connect it to your on-premises network using a VPN gateway.
- You can also use VNets to create subnets, which can be used to segment your network and control access to resources.
- Additionally, you can use VNets to assign custom IP addresses, create network security groups, and route traffic between subnets.

### Subnet in Azure

- A subnet is a range of IP addresses within a virtual network.
- Subnets are used to segment a virtual network into smaller, more manageable sections, and to control access to resources within the virtual network.
- Each subnet can have its own security rules, such as firewall rules, and can be used to host different types of resources, such as virtual machines, load balancers, and virtual appliances.
- Subnets can also be used to control access to resources in Azure by using network security groups (NSGs) and route tables.

To create a Vnet and set up a subnet on the created Vnet in Azure, you can use the Azure Portal, Azure CLI, or Azure PowerShell.

Here is an example of how to create a Vnet and a subnet using Azure CLI:

First, log in to your Azure account using the command **_az login_**

Create a resource group with the command

    az group create --name myResourceGroup --location eastus

Create a Vnet with the command

    az network vnet create --resource-group myResourceGroup --name myVnet --address-prefix 10.0.0.0/16

Create a subnet with the command

    az network vnet subnet create --resource-group myResourceGroup --vnet-name myVnet --name mySubnet --address-prefix 10.0.1.0/24

Verify the Vnet and subnet with the command

    az network vnet show --resource-group myResourceGroup --name myVnet

### Tutorial Link:

- [How to Create Azure Virtual Network and Subnet](https://www.youtube.com/watch?v=7mn8WDoAMJU&t=2s)
