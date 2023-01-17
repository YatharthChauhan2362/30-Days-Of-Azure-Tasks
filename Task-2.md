# 1. Create Private and Public Subnets in the above created Vnet

Virtual network (VNet) is a representation of a network in the cloud. Within a VNet, you can create one or more subnets. These subnets can be either private or public.

1. Private subnet:

- Subnet that does not have direct internet access. Only resources within the VNet can communicate with resources in a private subnet.
- This is useful for resources that do not need to be publicly accessible, such as database servers.

2. Public subnet:
   - Subnet that has direct internet access. This means that resources within the subnet can be accessed from the internet.
   - This is useful for resources that need to be publicly accessible, such as web servers.

By default, all resources in Azure are associated with a public IP address, which allows them to communicate with the internet. However, you can also assign private IP addresses to resources in a VNet, which allows them to communicate only with other resources within the VNet.

# 2. Create a VM and attach multiple NIC with it
