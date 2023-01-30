# TASK-7

# 1. Create a Site-to-Site on Azure and explore the use case of Site-to-Site VPN gateway and figure out how Site-to-Site VPN is different from Point-to-Site VPN?

Azure Virtual Network (VNet) enables you to create a virtual network in Azure and securely connect it to your on-premises network using a Site-to-Site VPN. 
 
- The VPN gateway in Azure acts as the VPN termination point on the Azure side of the connection and the on-premises VPN device acts as the VPN termination point on the on-premises side of the connection.

### Create a Site-to-Site (S2S) Connection

1.	Create a virtual network (VNet) in Azure: 
- This will serve as the on-premises location for the S2S connection.

2.	Create a virtual network gateway: 
- This will be the endpoint for the S2S connection on the Azure side.

3.	Create a local network gateway: 
- This will be the endpoint for the S2S connection on the on-premises side.

4.	Create a connection: 
- This will link the virtual network gateway and the local network gateway.

5.	Configure your on-premises router: 
- This will be used to establish the S2S connection.

6.	Verify the S2S connection: 
- This will ensure that the connection is working properly.

It would be helpful to have a basic understanding of Azure VNet and VPN gateway concepts. You can refer to Azure's documentation for detailed instructions on how to create a Site-to-Site connection in Azure.

### Use Case of Site-to-Site VPN Gateway

A common use case for a Site-to-Site VPN gateway on Azure is to connect an on-premises network to an Azure virtual network. 

This allows for seamless communication between resources on both networks, such as sharing files and databases, and accessing remote resources as if they were on the same network.

- For example, a company may have an on-premises network with a database server and a production line that needs to be connected to an Azure virtual network for remote monitoring and control. By creating a Site-to-Site VPN gateway on Azure, the company can securely connect the on-premises network to the Azure virtual network and access the database server and production line from anywhere, as long as they have an internet connection.

- Another use case is when a company wants to move some of its applications and resources to the cloud, but still needs to keep some of its sensitive data on-premises. By creating a Site-to-Site VPN gateway on Azure, the company can securely connect its on-premises network to the Azure virtual network, and move its applications and resources to the cloud while still maintaining control over its sensitive data.

- In summary, Site-to-Site VPN gateway on Azure enables companies to connect and secure their on-premises network with Azure Virtual network, allowing them to access and share resources and data across both networks. This can help companies to reduce costs, improve security and increase business agility.


### Tutorial Link:

[Azure Site To Site (S2S) VPN Configuration](https://www.youtube.com/watch?v=hKgEjqTp8MI)