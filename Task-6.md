# TASK-6

# 1. Learn about VPNs and their types

Azure VPN is a virtual private network (VPN) service provided by Microsoft Azure. 

- It allows users to securely connect to resources in Azure by creating a secure connection between their device and an Azure Virtual Network. 
- This allows users to access resources on the Azure Virtual Network as if they were on the same local network. 
- Azure VPN supports various VPN protocols such as Point-to-Site, Site-to-Site, and ExpressRoute. Additionally, Azure VPN also offers features such as network traffic management, and integration with Azure AD for identity management.

### Types of Azure VPN
There are several types of VPNs that can be created in Azure:

1.	Point-to-Site (P2S): 

- This type of VPN allows individual clients to connect to an Azure Virtual Network from a remote location. 
- It uses Secure Socket Tunneling Protocol (SSTP) or Internet Protocol security (IPsec) to establish the connection.
  
2.	Site-to-Site (S2S): 

- This type of VPN allows for a connection between an on-premises network and an Azure Virtual Network. 
- It uses IPsec to establish the connection.

3.	ExpressRoute: 

- This type of VPN uses a dedicated, private connection between an Azure datacenter and an on-premises network or another cloud provider, such as Amazon Web Services (AWS). 
- It uses a private connection that bypasses the public internet, providing better security and performance.

4.	VNet-to-VNet: 

- This type of VPN allows for a connection between two Azure Virtual Networks. 
- It uses IPsec to establish the connection.

5.	Multi-Site: 

- This type of VPN allows for a connection between multiple on-premises sites and an Azure Virtual Network.

6.	Azure Virtual WAN: 

- This is a service that enables you to connect your branches to Azure and to each other using a hub-spoke model, this allows you to have a secure and fast connection between all your branches and Azure.

### Azure VPN Gateway

Azure VPN Gateway is a service provided by Microsoft Azure that enables you to create a VPN connection between your on-premises network and an Azure Virtual Network (VNet). 

- The VPN Gateway acts as the endpoint on the Azure side of the connection, and it can be configured to use various VPN protocols such as Point-to-Site (P2S), Site-to-Site (S2S), ExpressRoute, VNet-to-VNet, and Multi-Site.

- Azure VPN Gateway uses the Internet Protocol security (IPsec) protocol to encrypt and secure the connection between your on-premises network and the Azure VNet. This allows you to securely access resources on the Azure VNet as if you were on the same local network.

- Additionally, the Azure VPN Gateway also offers features such as network traffic management, load balancing, and integration with Azure AD for identity management. It also supports BGP (Border Gateway Protocol) for more advanced network configurations.

- You can create a VPN Gateway in the Azure portal, using Azure PowerShell, or with Azure CLI.


### Tutorial Link:

- [Azure VPN and Azure VPN Gateway](https://youtu.be/ne8q0Lcc8gg)

# 2. Create Point to Site on Azure, A Point-to-Site (P2S) VPN gateway lets you create a secure connection to your virtual network from an individual computer

Azure Point-to-Site (P2S) VPN is a VPN connection that allows users to connect to an Azure virtual network from their personal devices. 

1.	Create a virtual network in Azure: 
- Go to the Azure portal and navigate to Virtual Networks. Click on +Add to create a new virtual network.

2.	Configure the virtual network: 
- Provide a name for the virtual network and select the appropriate subscription, resource group, and location.

3.	Create a gateway subnet: 
- In the virtual network configuration, create a new subnet called GatewaySubnet.

4.	Create a virtual network gateway: 
- Navigate to Virtual Network Gateways in the Azure portal and click on +Add. Select Point-to-site for the gateway type.

5.	Configure the virtual network gateway: 
- Provide a name for the gateway, select the appropriate subscription, resource group, and virtual network.

6.	Generate a root certificate: 
- Go to the Certificates & secrets section in the virtual network gateway configuration and click on Generate/Download root certificate.

7.	Download the VPN client: 
- Go to the Point-to-site configuration section and click on Download VPN client.

8.	Install the VPN client on client machines: 
- Install the VPN client on the machines that will be used to connect to the virtual network.

9.	Connect to the virtual network: 
- On the client machine, open the VPN client and enter the VPN server address. Click on Connect and enter the credentials for the virtual network.

10.	Verify the connection: Verify that the connection is successful by checking the status of the VPN connection in the VPN client.

Note: The above steps are a high-level overview and may vary depending on the specific requirements of your environment. Consult Azure documentation for detailed instructions on configuring P2S.


### Tutorial Link:

- [Azure Point To Site (P2S) VPN Configuration](https://youtu.be/wtrLparqino)
