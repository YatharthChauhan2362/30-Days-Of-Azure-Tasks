# TASK-4
# 1. Create 4 VNets

To create 4 VNets in Azure, you can use the Azure Portal, Azure PowerShell, or Azure CLI. Here are the basic steps for creating a VNet using the Azure Portal:

1. Sign in to the Azure portal (portal.azure.com).

2. In the left navigation pane, select "Create a resource."

3. Search for "Virtual Network" and select it from the results.

4. Fill in the required fields, such as the name, address space, and subscription.

5. Select the "Create" button to create the VNet.

Repeat the above steps for the rest of the VNets you want to create.

Alternatively, you can use Azure PowerShell or Azure CLI to automate the process of creating multiple VNets.


# 2. Management Vnet (HUB)

A management VNet, also known as a hub VNet, is a virtual network in Azure that is used to centrally manage and secure resources in one or more connected VNets, also known as spoke VNets. 

- The hub VNet acts as a central point of connectivity for the spoke VNets, allowing resources in the spoke VNets to communicate with each other and with resources in the hub VNet.

Here are the basic steps for creating a management VNet using the Azure Portal:

1. Sign in to the Azure portal (portal.azure.com).
   
2. In the left navigation pane, select "Create a resource."

3. Search for "Virtual Network" and select it from the results.

4. Fill in the required fields, such as the name, address space, and subscription.

5. In the "Advanced" section, select "Add a virtual network" to create a hub-spoke topology.

6. Select the "Create" button to create the VNet.

Once the management VNet is created, you can then create and connect spoke VNets to it using the same process.

You can also use Azure PowerShell or Azure CLI to create the management VNet and connect the spoke VNets to it.

With Azure Policy, Azure role-based access control (RBAC), and Azure Firewall you can secure and manage your management Vnet.

# 3. Production Vnet

A production VNet in Azure is a virtual network that is used to host production workloads, such as web servers, databases, and other mission-critical resources. 

- It is a dedicated and isolated network environment that allows organizations to securely connect and manage their production resources within Azure. 
- The production VNet typically includes subnets for different types of resources, such as web servers, databases, and load balancers. 
- It can also include security features such as network security groups, firewall rules, and VPN connections. 
- The production VNet is typically separate from other VNets such as development and testing VNets to ensure that production resources are protected from any potential security threats or accidental changes from other environments.


# 4. Testing Vnet

A Testing VNet in Azure is a virtual network that is used for testing and development purposes. 
- It is a separate network environment that is isolated from the production network and allows for testing of new configurations, updates, and deployments without affecting the production environment. 
- The Testing VNet can be used to test new software, applications, and updates before they are deployed to the production network. 
- This helps ensure that any issues or bugs are identified and resolved before they can cause problems in the production environment. 
- Additionally, the Testing VNet can be used to test disaster recovery plans and network configurations, ensuring that they are effective and reliable before they are implemented in the production network.

# 5. Developing Vnet and Configure Hub and Spoke Architecture and verify it's working by launching VM in each VNet and ping from Management VM to every other VM.

1.	Log in to the Azure portal (https://portal.azure.com/)

2.	Click on the "Create a resource" button in the top left corner of the portal

3.	In the search bar, type "Virtual Network" and select the "Virtual Network" option from the list

4.	Click the "Create" button

5.	In the "Basics" tab, enter a name for the virtual network, select the subscription and resource group you want to use. Make sure you name it developing Vnet for easy identification.

6.	In the "Address space" tab, enter the IP address range for the virtual network. This is the range of IP addresses that will be available for use within the virtual network.

7.	In the "Subnets" tab, create a new subnet for the developing VNet. This subnet will be used for all developing resources, such as virtual machines, load balancers, and network interfaces.

8.	In the "Security" tab, you can configure the security settings for the virtual network. This includes firewall rules, network security groups, and VPN connections.

9.	In the "Tags" tab, you can add any tags that you want to use to organize your virtual network.

10.	Click the "Review + Create" button to review the configuration, and then click "Create" to create the virtual network.

11.	Wait for the virtual network to be created. This process may take a few minutes.

12.	Once the virtual network is created, you can navigate to the virtual network in the Azure portal to view and manage it.

13.	Now you have to create Hub and spoke architecture. To do that, you need to create Hub VNet and then connect it to multiple spoke VNets.

14.	To create a Hub VNet, go to the Azure portal, and click on the "Create a resource" button. Select "Virtual Network" and click "Create".

15.	In the "Basics" tab, enter a name for the hub VNet, select the subscription and resource group.

16.	In the "Address space" tab, enter the IP address range for the hub VNet.

17.	In the "Subnets" tab, create a new subnet for the hub VNet. This subnet will be used for all hub resources, such as virtual machines, load balancers, and network interfaces.

18.	In the "Security" tab, you can configure the security settings for the hub VNet. This includes firewall rules, network security groups, and VPN connections.

19.	In the "Tags" tab, you can add any tags that you want to use to organize your hub VNet.

20.	Click the "Review + Create" button to review the configuration, and then click "Create" to create the hub VNet.

21.	Now you have to connect the spoke VNets to the hub VNet. Go to the Azure portal and select the spoke VNet that you want to connect.

22.	In the spoke VNet, go to the "Connectivity" tab, and click on the "Add" button to add a new connection.

23.	Select "Virtual Network" as the connection type and enter the details of the hub VNet.

24.	Click "Save" to create the connection.

25.	Repeat steps 21-24 for all spoke VNets that you want to connect to the hub VNet.

26.	Once you have created the hub and spoke architecture, you can now launch virtual machines in each VNet

Once the VMs are created, you can use the ping command to test connectivity between the management VM and the other VMs.

The ping command sends an ICMP echo request packet to the specified IP address and waits for a response. If the response is received, the connection is considered successful.

It's important to note that, in order to ping between VMs, you will need to configure the appropriate network security rules to allow ICMP traffic.


### Tutorial Link:

- [Create a virtual network (VNet)](https://www.youtube.com/watch?v=zIdwpFZQfmk)
- [Virtual Network Manager - Hub and Spoke Network Topology](https://www.youtube.com/watch?v=-d0aa3GkTK0)


