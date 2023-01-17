# 1. Create multiple VMs (i.e.) VM1 and VM2 in two different Virtual networks.

To create multiple VMs (VM1 and VM2) in two different Virtual networks in Azure, you can follow these steps:

- Log in to the Azure portal ***https://portal.azure.com/***

- Click on the "Create a resource" button and select "Windows Server" or "Linux" as the operating system for the VMs.

- Fill out the basic settings for the VM, such as the name, size, and username/password.

- In the "Advanced" tab, you can select the virtual network and subnet that the VM will be created in.

- Repeat steps 2-4 to create the second VM (VM2) and make sure to select a different virtual network for it.

- Once the VMs are created, you can verify that they are in different virtual networks by going to the "Virtual machines" page in the Azure portal, and checking the virtual network and subnet information for each VM.

Note: Make sure you have sufficient permissions to create and manage virtual networks, virtual machines, and other resources in your Azure subscription.

# 2. Create a Network Security Group to establish connection among VMs to ping each other and understand how the priority works

To create a Network Security Group (NSG) to establish connection among VMs to ping each other, and understand how the priority works, you can follow these steps:

- Log in to the Azure portal ***https://portal.azure.com***

- Go to the "Network security groups" page and click on the "Add" button to create a new NSG.

- Fill out the basic information for the NSG, such as the name and resource group.

- Click on the "Inbound security rules" tab and create a new rule.

- In the new rule, set the "Source" to "Virtual network" and select the virtual network that your VMs are in.

- Set the "Destination" to "Virtual network" and select the same virtual network.

- Set the "Protocol" to "ICMP" and the "Source port ranges" and "Destination port ranges" to "\*"

- In the "Priority" field, you can assign a priority number to this rule (e.g. "100"). Higher priority rules are evaluated before lower priority rules.

- Repeat step 4-8 for the outbound security rule

- Once the NSG is created, you should be able to ping between VMs in the same virtual network.

- To understand how priority works, you can create multiple rules with different priority numbers and test the connectivity between the VMs. The rule with the highest priority number will take precedence over the others.

Note: Make sure that the VMs are in the same Virtual Network, and NSG is associated with the same subnet.

### Tutorial Link:

- [How to Create Network Security Group, Associate with VM & Subnet](https://www.youtube.com/watch?v=Lxy3ZxFMUlM)
