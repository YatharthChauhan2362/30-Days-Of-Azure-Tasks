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

### To create a Vnet and set up a subnet on the created Vnet in Azure, you can use the Azure Portal, Azure CLI, or Azure PowerShell.

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

# 2. Create a VM on the subnet and access VM

To create a VM on a subnet in Azure, you can use the Azure Portal, Azure PowerShell, or Azure CLI.

Here are the general steps for creating a VM in Azure using the Azure Portal:

- Log in to the Azure Portal **_(https://portal.azure.com/)_**
- Click on the "Create a resource" button on the top left corner of the screen.
  In the search bar, type "Windows Server" and select the latest version of the Windows Server operating system.
- Fill in the required fields for the VM, including the subscription, resource group, and VM name.
  Under the "Settings" section, select the subnet where you want to create the VM.
- Select the size of the VM that you want to use.
- Click on the "Review + Create" button to review the settings and create the VM.
- Wait for the VM to be created, then go to the VM overview page and click on the "Connect" button to access the VM using Remote Desktop Protocol (RDP).
- Once you are connected to the VM, you can use the VM as you would use any other Windows machine.

To communicate with two Virtual Machines (VMs) in the same Virtual Network (VNet):

- You can use the internal IP addresses of the VMs. These IP addresses are automatically assigned by Azure and are only accessible within the VNet.
- You can also use the hostnames of the VMs if you have set them up.
- Additionally, you can create Network Security Groups (NSGs) to control inbound and outbound traffic to the VMs.

### Tutorial Link:

- [How to communicate with two VM's in same VNet](https://www.youtube.com/watch?v=qrdxYBgHi5A)
