# TASK-8

# 1. Create a Vnet with 2 Subnets

### Azure Portal

1.	Log in to the Azure portal (https://portal.azure.com/)

2.	Click on the "Create a resource" button in the top left corner of the screen.

3.	In the search bar, type "Virtual Network" and select it from the list.

4.	In the Virtual Network pane, fill in the required fields, such as "Name" and "Subscription".

5.	Under "Address space", add two CIDR blocks for the subnets you want to create, for example: 10.0.0.0/16 for the VNet and 10.0.1.0/24 and 10.0.2.0/24 for the 2 subnets.

6.	Under the "Subnets" section, click on the "+Add" button to create the first subnet. In the "Name" field, give it a name and in the "Address range" field enter the CIDR block for the first subnet. Repeat this step for the second subnet.

7.	Review your settings and click on "Create" to create the VNet and subnets.

8.	Wait for the deployment to complete. Once it is completed, you can find your VNet and subnets under the "Virtual Networks" section in the Azure portal.

Note: This is just an example, you can customize the name, location and IP addresses as per your requirement.


### Azure CLI:
   
First, create a resource group with the following command:


    az group create --name MyResourceGroup --location eastus

Next, create a VNet with the following command:


    az network vnet create --resource-group MyResourceGroup --name MyVnet --address-prefix 10.0.0.0/16

Create the first subnet within the VNet with the following command:


    az network vnet subnet create --resource-group MyResourceGroup --vnet-name MyVnet --name MySubnet1 --address-prefix 10.0.1.0/24
    
Create the second subnet within the VNet with the following command:


    az network vnet subnet create --resource-group MyResourceGroup --vnet-name MyVnet --name MySubnet2 --address-prefix 10.0.2.0/24


# 2. Web-Tier: Linux VM, Windows VM.

A web tier in Azure refers to the infrastructure and services that are used to host and deliver web applications. This can include a variety of Azure services and tools, such as:

Azure Virtual Machines (VMs) - 

- VMs can be used to host web servers such as IIS, Apache, or Nginx, and can run a variety of operating systems including Windows and Linux.

Azure App Service: 

- This is a fully managed platform that allows you to build, deploy, and scale web apps and APIs. It supports a variety of programming languages and frameworks, including .NET, Java, Node.js, Python, and more.

Azure Functions: 

- These are event-driven, serverless compute services that can be used to run code in response to specific events, such as an HTTP request or a change in data.

Azure Content Delivery Network (CDN): 

- This service can be used to deliver content, such as images, videos, and other static files, to users with low latency and high throughput.

Azure Load Balancer: 

- This service can be used to distribute incoming traffic across multiple VMs or other resources to improve performance and availability.

Azure Traffic Manager: 

- This service can be used to route traffic to different endpoints based on rules and policies, such as geographic location or endpoint health.

These are just a few examples of the many services and tools that can be used to create a web tier in Azure. The specific combination of services used will depend on the requirements of the web application and the desired level of scalability, performance, and availability.

### Windows Virtual Machine (VM)

A Windows Virtual Machine (VM) can be used as a web tier in Azure to host web applications and services. Here are the general steps to set up a Windows VM as a web tier in Azure:

1.	Create a new Azure Virtual Machine using the Azure Portal, Azure PowerShell, or Azure CLI. You can use an existing image or create a custom image with the necessary software and configurations.

2.	Configure the network settings for the VM, including a public IP address and a network security group to control inbound and outbound traffic.

3.	Install and configure a web server, such as Internet Information Services (IIS), on the VM.

4.	Install and configure any necessary web applications or services, such as .NET or PHP.

5.	Create and configure any necessary storage, such as Azure Storage or Azure Files, for the VM to use.

6.	Create and configure any necessary backups for the VM.

7.	Test the web application or service to ensure that it is working correctly.

8.	Monitor the VM and the web application or service to ensure that they are running correctly and to troubleshoot any issues that may arise.

9.	Scale the VM as necessary to handle increased traffic or load.



It's also important to note that Azure offers several services that can be used to improve the security, performance, and scalability of a Windows VM web tier, such as Azure Load Balancer, Azure Traffic Manager, Azure Front Door, Azure Content Delivery Network (CDN) and Azure Application Gateway. 

These services can be used to distribute traffic, optimize content delivery, and provide additional security and scalability features.

### Linux Virtual Machine (VM)

Creating a Linux VM web tier in Azure involves several steps:

1.	Choose a Linux distribution: Azure supports a variety of Linux distributions, such as Ubuntu, CentOS, and Debian. You will need to choose a distribution that is compatible with your web application and has the necessary dependencies installed.

2.	Create a Virtual Machine: You can use the Azure Portal, Azure CLI, or Azure PowerShell to create a new VM. You will need to provide a name for the VM, choose a size, and select the Linux distribution you want to use.

3.	Configure Networking: You will need to configure the VM's network settings, such as assigning it to a virtual network and subnet, and configuring security groups and public IPs.

4.	Install and configure web server: Once the VM is created, you will need to connect to it and install a web server such as Apache or Nginx. You will also need to configure the web server to serve your web application.

5.	Deploy your web application: Once the web server is configured, you will need to deploy your web application to the VM. This can involve copying files to the VM, or using a deployment tool such as Git or Jenkins.

6.	Monitoring and scaling: To ensure the availability and performance of your web application, you should monitor the performance of your VM and web server, and scale the VM up or down as necessary.

It's important to note that, before you start creating your Linux VM, you should plan and design your infrastructure and networking accordingly, taking into consideration the security, availability, scalability and compliance of your web tier. Also, it's important to keep the operating system and software up to date, configure backups and monitoring and test your disaster recovery plan.


# 3. Data-Tier: SQL DB

The data tier refers to the portion of a cloud-based application that is responsible for storing and managing data. 

- This can include databases, storage systems, and other data management tools. Azure offers a variety of data tier services, such as Azure SQL Database, Azure Cosmos DB, and Azure Blob Storage, that can be used to build and manage data-intensive applications in the cloud. 
- These services can be easily scaled and configured to meet the specific needs of an application, and can be integrated with other Azure services, such as Azure Virtual Machines and Azure App Service, to build complete cloud-based solutions.

### SQL DB Data-Tier

SQL DB Data-Tier in Azure refers to the use of Azure SQL Database as the data storage solution for an application or service. 
- This allows for easy management and scalability of the database, as well as integration with other Azure services such as Azure Data Factory and Azure Data Lake Storage. Additionally, Azure SQL Database provides built-in security features such as encryption and Azure Active Directory authentication, making it a secure choice for storing sensitive data.



# 4. Launch VMS into Availability Set

An Availability Set in Azure is a feature that ensures that virtual machines (VMs) running in a set are deployed across different physical locations within a datacenter, known as fault domains and update domains.
- This ensures that if a hardware or software failure occurs within one fault domain or update domain, the VMs within the Availability Set will continue to operate, providing high availability for the application or service. This feature is especially useful for mission-critical workloads that require minimal downtime.

- When creating an Availability Set, you can specify the number of fault domains and update domains you want to use. 
- This will determine the number of physical locations your VMs will be deployed to. 
- For example, if you specify two fault domains and two update domains, your VMs will be deployed across four different physical locations.

- By using an Availability Set, you can ensure that your VMs are protected against unplanned maintenance and infrastructure failures, providing a high availability solution for your application or service.

### Tutorial Link:

- [Deploy Azure Virtual Machines In Availability Set & Avaiability Zone](https://www.youtube.com/watch?v=YUOgcB339iA&ab_channel=K21Academy)


