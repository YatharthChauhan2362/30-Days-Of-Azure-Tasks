# TASK-5

# 1. Learn about Load balancer and their types

Azure Load Balancer is a fully managed service in Azure that enables you to distribute incoming traffic across multiple virtual machines (VMs) in a load-balanced set. 
- The load balancer distributes incoming traffic across VMs in the load-balanced set based on a configurable algorithm, such as round-robin or least connections. 
- This helps ensure that no single VM is overwhelmed with too much traffic, and that all VMs are utilized effectively.

1. Basic Load Balancer 

- It is a Layer 4 load balancer that uses a hash algorithm to distribute incoming network traffic to different virtual machines. It is a cost-effective option and is best suited for simple load balancing scenarios.

2. Standard Load Balancer
 
- It is a Layer 7 load balancer that can route network traffic based on the content of the request, such as a specific IP address or URL path. It also provides additional features such as SSL offloading and cookie-based session affinity. It is a more feature-rich option and is best suited for more complex load balancing scenarios.

Both Load balancer types supports TCP, UDP, and TCP over SSL protocols.



# 2. Create an Internal and External Load Balancer.

Azure Load Balancer supports two types of load balancing:

External load balancing: 
   
- Distributes incoming traffic to VMs from the internet or from other external networks.

Internal load balancing: 

- Distributes incoming traffic to VMs within a virtual network.

- Azure Load Balancer also provides health probes to monitor the health of VMs, and automatically redirects traffic away from any unhealthy VMs.

- Azure Load Balancer is a highly available service and automatically scales to match the number of incoming requests. It can be easily configured and managed through Azure Resource Manager templates, Azure PowerShell, Azure CLI, and Azure portal.

### Create an Internal Load Balancer

To create an internal load balancer in Azure, you can use the Azure portal, Azure PowerShell, Azure CLI, or an Azure Resource Manager template. 

Here is an example of how to create an internal load balancer using the Azure portal:

1.	Open the Azure portal and navigate to the virtual network where you want to create the load balancer.

2.	Click on "+Create a resource" and search for "Load Balancer" then select it.

3.	Select "Internal" as the "Type" of the Load Balancer and fill in the other required information such as name, subscription, resource group, IP version and location.

4.	In the "Frontend IP Configuration" section, create a new IP address and give it a name.

5.	In the "Backend pools" section, add the virtual machines that you want to balance the traffic among them.

6.	In the "Health probes" section, create a new health probe and configure it to monitor the health of the VMs.

7.	In the "Load balancing rules" section, create a new rule and configure it to distribute incoming traffic to the VMs in the backend pool using the desired algorithm.

8.	Review the settings and click on "Create" to deploy the internal load balancer.

Once the load balancer is created, you can monitor and manage it through the Azure portal.

Note: The above steps are general and can vary based on the specific requirements of your load balancing scenario and the Azure services you are using.

### Create an External Load Balancer

To create an external load balancer in Azure, you can use the Azure portal, Azure PowerShell, Azure CLI, or an Azure Resource Manager template. Here is an example of how to create an external load balancer using the Azure portal:

1.	Open the Azure portal and navigate to the virtual network where you want to create the load balancer.

2.	Click on "+Create a resource" and search for "Load Balancer" then select it.

3.	Select "Public" as the "Type" of the Load Balancer and fill in the other required information such as name, subscription, resource group, IP version and location.

4.	In the "Frontend IP Configuration" section, create a new IP address and give it a name.

5.	In the "Backend pools" section, add the virtual machines that you want to balance the traffic among them.

6.	In the "Health probes" section, create a new health probe and configure it to monitor the health of the VMs.

7.	In the "Load balancing rules" section, create a new rule and configure it to distribute incoming traffic to the VMs in the backend pool using the desired algorithm.

8.	In the "Inbound NAT rules" section, create a new NAT rule to allow incoming traffic to reach specific ports on the VMs in the backend pool.

9.	Review the settings and click on "Create" to deploy the external load balancer.

Once the load balancer is created, you can monitor and manage it through the Azure portal.

Note: The above steps are general and can vary based on the specific requirements of your load balancing scenario and the Azure services you are using. Also, you need to configure Azure firewall or a Network Virtual Appliance (NVA) to allow traffic from the internet to reach your load balancer.


### Tutorial Link:

- [Internal Load Balancer - Demo](https://www.youtube.com/watch?v=VNJ1QZ-mh7Y)

- [External(Public) Load Balancer - Demo](https://www.youtube.com/watch?v=QeMet5yepQ0)