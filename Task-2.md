# 1. Create Private and Public Subnets in the above created Vnet

Virtual network (VNet) is a representation of a network in the cloud. Within a VNet, you can create one or more subnets. These subnets can be either private or public.

### Private Subnet:

- Subnet that does not have direct internet access. Only resources within the VNet can communicate with resources in a private subnet.
- This is useful for resources that do not need to be publicly accessible, such as database servers.

### Public Subnet:

- Subnet that has direct internet access. This means that resources within the subnet can be accessed from the internet.
- This is useful for resources that need to be publicly accessible, such as web servers.

By default, all resources in Azure are associated with a public IP address, which allows them to communicate with the internet. However, you can also assign private IP addresses to resources in a VNet, which allows them to communicate only with other resources within the VNet.

To create private and public subnets in an existing VNet in Azure, you can use the Azure Portal, Azure CLI, or Azure PowerShell.

### Azure Portal:

- Log in to the Azure Portal and navigate to the virtual network you want to create the subnets in.
- Select "Subnets" under the "Settings" section.
- Click the "+Add" button to create a new subnet.
- In the "Name" field, enter a name for the subnet (e.g. "PrivateSubnet").
- In the "Address range" field, enter the range of IP addresses for the subnet (e.g. 10.0.1.0/24).
- Select the virtual network from the "Virtual network" drop-down menu.
- Select the "No" for "Assign public IP address" for the private subnet
- Repeat the above steps for creating Public subnet, but select "yes" for "Assign public IP address"

### Azure CLI:

- Open a command-line interface and log in to your Azure account using the "az login" command.
- Use the "az network vnet subnet create" command to create the private subnet and specify the VNet name, subnet name, and IP address range.

e.g:

    az network vnet subnet create --vnet-name MyVNet --name PrivateSubnet --address-prefix 10.0.1.0/24

- Use the same command to create the public subnet and specify the VNet name, subnet name, and IP address range

e.g:

    az network vnet subnet create --vnet-name MyVNet --name PublicSubnet --address-prefix 10.0.2.0/24

### Azure PowerShell:

- Open a PowerShell prompt and log in to your Azure account using the "Connect-AzAccount" command.
- Use the "New-AzVirtualNetworkSubnetConfig" cmdlet to create a new subnet configuration for the private subnet and specify the name and IP address range

e.g.

    New-AzVirtualNetworkSubnetConfig -Name PrivateSubnet -AddressPrefix 10.0.1.0/24

- Use the "New-AzVirtualNetworkSubnet" cmdlet to create the private subnet and specify the VNet name and the subnet configuration created above

e.g.

    New-AzVirtualNetworkSubnet -Name PrivateSubnet -VirtualNetwork $vnet -AddressPrefix 10.0.1.0/24

- Repeat the above steps for creating public subnet

### Tutorial Link:

- [Azure Vnet Creations With Public and Private Subnets](https://www.youtube.com/watch?v=tv49WXZOAWM)

# 2. Create a VM and attach multiple NIC with it

A Network Interface Card (NIC) in Azure is a virtual network adapter that is used to connect a virtual machine (VM) or a scale set to a virtual network (VNet) and to the internet.

- A NIC enables communication between the VM or scale set and other resources within the VNet, as well as with resources outside the VNet, such as the internet.

- Each NIC has a unique IP address and can be associated with one or more IP configurations, each of which has its own IP address and subnet. The NIC can also be associated with one or more security groups, which can be used to control inbound and outbound network traffic.

- When you create a virtual machine in Azure, a NIC is automatically created and associated with the VM. You can also create additional NICs and associate them with a VM if needed.

- You can create, view, and manage NICs using the Azure Portal, Azure CLI, Azure PowerShell, or Azure SDKs.

It's worth noting that NICs are not only used for virtual machines, but also for other resources such as Azure Kubernetes Services (AKS) and Azure App Service, which also need network connectivity.

- Log in to the Azure portal ***https://portal.azure.com***

- Click on the "Create a resource" button in the top left corner of the screen

- In the search bar, type "virtual machine" and select the "Virtual Machines" option from the list

- On the "Create a virtual machine" page, fill in the required information such as VM name, region, and resource group

- Under "Size", select a size that meets your requirements and supports multiple NICs

- In the "Networking" section, select "Add NIC" to add additional NICs to the VM

- Fill in the required information for each NIC, such as the name, IP configuration, and virtual network

- Once all NICs have been added, click on the "Review + create" button to review the settings

- On the "Review + create" page, verify that all information is correct and click on the "Create" button to create the VM

- Wait for the deployment to complete and then go to the VM's "Networking" tab to verify that the NICs have been attached correctly.

### Tutorial Link:

- [Azure VM with multiple network interface (NIC)](https://www.youtube.com/watch?v=xOnqZsLvN_E)
