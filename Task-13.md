# 1. Create a Bridge Network.

1.	Log in to the Azure portal (portal.azure.com).
2.	Select "Virtual networks" from the left-hand navigation menu.
3.	Click the "+Add" button to create a new virtual network.
4.	Fill in the required information, such as the virtual network name, address space, and subscription.
5.	Under "IPv4 address space," enter a range of IP addresses for the virtual network.
6.	Under "Subnets," click the "+Add" button to create a new subnet.
7.	Fill in the required information, such as the subnet name and address range.
8.	In the "Advanced" section, you can configure the Azure firewall, Azure DDoS Protection, and Azure Virtual WAN.
9.	Click the "Review + create" button to review your settings, and then click the "Create" button to create the virtual network.

Note:

- You can also use Azure Cloud Shell or Azure CLI to create a bridge network.
- You might have to create a route table, or associate the subnet to an existing route table, to route the traffic to on-premises network.
- You can also use Network Security Group to secure the network.
- The above steps are general and you might have to follow the specific steps according to the version of the Azure and the specific requirements of your application.

# 2. Launch two Docker Containers

Here are the general steps to launch two Docker containers in Azure:
1.	Log in to the Azure portal (portal.azure.com).
2.	Select "Container instances" from the left-hand navigation menu.
3.	Click the "+Add" button to create a new container instance.
4.	Fill in the required information, such as the container group name, subscription, resource group, and location.
5.	Under "Container 1" or "Container 2" section, provide the image name and the command to be executed when the container starts.
6.	Under "Advanced" section, you can configure the environment variables, ports, volume, and CPU/memory limits for the container.
7.	Click the "Review + create" button to review your settings, and then click the "Create" button to create the container instance.
8.	Once the container is created, you can see the status and other details of the container on the Container Instances page.



# 3. Assign both containers with same network

Here are the general steps to assign both containers with the same network in Azure:
1.	Log in to the Azure portal (portal.azure.com)
2.	Select "Virtual networks" from the left-hand navigation menu
3.	Select the virtual network that you want to use for your containers
4.	Select "Subnets" from the left-hand navigation menu
5.	Select the subnet that you want to use for your containers
6.	Select "Container instances" from the left-hand navigation menu
7.	Select the container instance that you want to assign to the subnet
8.	Under the "Networking" tab, you should see an option to "Associate with a subnet". Select the subnet that you want to associate with the container.
9.	Repeat the same steps for the second container instance
10.	Click "Save" to associate the container instances with the same subnet



# 4. Find out if this bridge network works like a switch between these two containers and like a router for any external IP.

A bridge network in Azure works like a virtual switch between containers running on the same host. When you create a bridge network, it allows the containers to communicate with each other using their IP addresses. This means that the containers can communicate with each other as if they were on the same physical network.

- In this case, if you have assigned the same bridge network to both containers, they should be able to communicate with each other using their IP addresses.

- As for the external IP, a bridge network does not act as a router for external IP addresses. In order for the containers to communicate with external IP addresses, you would need to use a different type of network such as a NAT network.

- You can use Azure Load Balancer, Azure Firewall, or Azure Application Gateway to provide internet access to the container.

- It's worth noting that Azure Container Instances only support bridge network mode.

- You can also use Azure Kubernetes Service (AKS) to deploy the container and assign the network, AKS support different network mode like bridge, host, and overlay.