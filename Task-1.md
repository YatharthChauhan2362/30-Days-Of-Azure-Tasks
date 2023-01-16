# 1. Create a Vnet and set up a subnet on the created Vnet

To create a Vnet and set up a subnet on the created Vnet in Azure, you can use the Azure Portal, Azure CLI, or Azure PowerShell.

Here is an example of how to create a Vnet and a subnet using Azure CLI:

First, log in to your Azure account using the command **az login**

Create a resource group with the command az group create --name myResourceGroup --location eastus

Create a Vnet with the command az network vnet create --resource-group myResourceGroup --name myVnet --address-prefix 10.0.0.0/16

Create a subnet with the command az network vnet subnet create --resource-group myResourceGroup --vnet-name myVnet --name mySubnet --address-prefix 10.0.1.0/24

Verify the Vnet and subnet with the command az network vnet show --resource-group myResourceGroup --name myVnet
