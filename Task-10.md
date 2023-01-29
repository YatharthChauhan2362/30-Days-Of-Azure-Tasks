# 1. Create a Vnet with single subnet and Create a VM.

To create a virtual network (VNet) with a single subnet and a virtual machine (VM) in Azure, you can use Azure Portal or Azure PowerShell or Azure CLI.

### Using Azure Portal:

1.	Go to the Azure portal (https://portal.azure.com/)
2.	Click on "Create a resource"
3.	Search for "Virtual Network" and select it
4.	Fill in the required information for the virtual network, such as name, resource group, and location
5.	Under "Subnets", click on "Add" to create a new subnet. Fill in the required information for the subnet, such as name and address range
6.	Click on "Review + create" to review the settings and then click on "Create" to create the virtual network

To create a VM using the Azure portal, follow these steps:

1.	Go to the Azure portal (https://portal.azure.com/)
2.	Click on "Create a resource"
3.	Search for "Windows Server" and select it
4.	Fill in the required information for the VM, such as name, resource group, location, and size
5.	Under "Settings", select the virtual network and subnet that you created in step 1
6.	Click on "Review + create" to review the settings and then click on "Create" to create the VM




<!-- ### Using Azure PowerShell:

1. First, log in to your Azure account using the Connect-AzAccount cmdlet.

2. Create a new resource group for your VNet and VM using the New-AzResourceGroup cmdlet. 

        New-AzResourceGroup -Name "MyResourceGroup" -Location "EastUS"

3. Create a new virtual network using the New-AzVirtualNetwork cmdlet.

        New-AzVirtualNetwork -Name "MyVNet" -ResourceGroupName "MyResourceGroup" -Location "EastUS" -AddressPrefix "10.0.0.0/16"

4. Create a new subnet within the virtual network using the New-AzVirtualNetworkSubnetConfig cmdlet. 

        $subnet = New-AzVirtualNetworkSubnetConfig -Name "MySubnet" -AddressPrefix "10.0.0.0/24"
        Add-AzVirtualNetworkSubnet -VirtualNetwork $vnet -Subnet $subnet

5. Create a new virtual machine using the New-AzVM cmdlet.

        New-AzVM -Name "MyVM" -ResourceGroupName "MyResourceGroup" -Location "EastUS" -VirtualNetworkName "MyVNet" -SubnetName "MySubnet" -SecurityGroupName "MySecurityGroup" -PublicIpAddressName "MyPublicIp"

6. Start the virtual machine using the Start-AzVM cmdlet.

        Start-AzVM -Name "MyVM" -ResourceGroupName "MyResourceGroup"

##### Using Azure CLI:

    az group create --name MyResourceGroup --location eastus    
    az network vnet create --name MyVNet --resource-group MyResourceGroup --address-prefix 10.0.0.0/16
    az network vnet subnet create --name MySubnet --resource-group MyResourceGroup --vnet-name MyVNet --address-prefix 10.0.0.0/24
    az vm create --name MyVM --resource-group MyResourceGroup --location eastus --vnet-name MyVNet --subnet MySubnet

Please make sure you have the latest Azure PowerShell and Azure CLI version installed on your machine, also Azure subscription and necessary permissions are required. -->



# 2. Schedule a Daily backup of VM at 3:AM using vault

To schedule a daily backup of a virtual machine (VM) at 3:00 AM using an Azure Backup vault, you can use Azure Portal, PowerShell or Azure CLI.

##### Using Azure Portal:

1.	Go to the Azure portal (https://portal.azure.com/)

2.	Click on "Resource groups" from the left navigation menu and select the resource group that contains the VM that you want to back up.

3.	Click on the name of the Recovery Services vault that you want to use for the backup. If you don't have a Recovery Services vault, you'll need to create one.

4.	Click on "Backup" from the left navigation menu and then click on "Back up"

5.	Select the virtual machine that you want to back up

6.	Select the backup policy you want to use, or create a new one.

7.	In the Schedule section, Select the schedule that best fits your needs

8.	Select the retention policy that you want to use

9.	Click on "Enable Backup"

10.	Confirm the settings and click on "Enable Backup"

<!-- 
##### Using Azure PowerShell:

1. First, log in to your Azure account using the Connect-AzAccount cmdlet.

2. Create a new Azure Backup vault using the New-AzRecoveryServicesVault cmdlet.

        New-AzRecoveryServicesVault -Name "MyBackupVault" -ResourceGroupName "MyResourceGroup" -Location "EastUS"


3. Register the Azure Backup extension on the VM using the Enable-AzRecoveryServicesBackup cmdlet.

        Enable-AzRecoveryServicesBackup -Name "MyVM" -ResourceGroupName "MyResourceGroup" -RecoveryServicesVault "MyBackupVault"

4. Create a new backup schedule for the VM using the New-AzRecoveryServicesBackupSchedule cmdlet. 

        New-AzRecoveryServicesBackupSchedule -Name "MyBackupSchedule" -RecoveryServicesVault "MyBackupVault" -WorkloadType "AzureVM" -Frequency "Daily" -StartTime "03:00"

5. Create a new backup policy for the VM using the New-AzRecoveryServicesBackupPolicy cmdlet.

        New-AzRecoveryServicesBackupPolicy -Name "MyBackupPolicy" -RecoveryServicesVault "MyBackupVault" -WorkloadType "AzureVM" -Schedule "MyBackupSchedule"

6. Associate the backup policy with the VM using the Set-AzRecoveryServicesBackupProtection cmdlet. 

        Set-AzRecoveryServicesBackupProtection -Name "MyVM" -ResourceGroupName "MyResourceGroup" -RecoveryServicesVault "MyBackupVault" -Policy "MyBackupPolicy"

##### Using Azure CLI:

    az backup vault create --name MyBackupVault --resource-group MyResourceGroup --location eastus
    az backup protection enable-for-vm --vm-name MyVM --resource-group MyResourceGroup --vault-name MyBackupVault
    az backup policy create --name MyBackupPolicy --resource-group MyResourceGroup --vault-name MyBackupVault --workload-type AzureVM --frequency Daily --start-time "03:00"
    az backup protection set-policy --policy-name MyBackupPolicy --resource-group MyResourceGroup --vault-name MyBackupVault --vm MyVM

Please make sure you have the latest Azure PowerShell and Azure CLI version installed on your machine, also Azure subscription and necessary permissions are required.

Also, note that the above commands sets up the schedule and policy but it doesn't initiate the backup, you will need to use Start-AzRecoveryServicesBackup or az backup protection backup to initiate the first backup. -->


# 3. Create an Alert rule for VM CPU percentage.

##### Using Azure Portal:

1.	Go to the Azure portal (https://portal.azure.com/)

2.	Click on "Monitor" from the left navigation menu

3.	Click on "Alerts"

4.	Click on "+ New alert rule"

5.	Select the subscription, resource group, and virtual machine that you want to create an alert for.

6.	Select the "Metric" condition type, and then select "Percentage CPU" as the metric

7.	Select "Greater than or equal to" as the condition and enter the threshold value for the CPU percentage

8.	Select the "Frequency" and "Period" for how often the rule should check the condition.

9.	Select the "Action Group" or create a new one

10.	Fill out the details for the alert rule, including the name and description, and click on "Create"


# 4. Criteria: CPU% More Than 80%, There Should be an alert on email.

##### Using Azure Portal:

1.	Go to the Azure portal (https://portal.azure.com/)

2.	Click on "Monitor" from the left navigation menu

3.	Click on "Alerts"

4.	Click on "+ New alert rule"

5.	Select the subscription, resource group, and virtual machine that you want to create an alert for.

6.	Select the "Metric" condition type, and then select "Percentage CPU" as the metric

7.	Select "Greater than" as the condition and enter the threshold value 80 for the CPU percentage

8.	Select the "Frequency" and "Period" for how often the rule should check the condition.

9.	Select the "Action Group" or create a new one.

10.	In the Action Group, Select "Add action" and choose Email/SMS/Push/Voice as an action type

11.	Fill the email Id/ phone number where you want to receive an alert

12.	Fill out the details for the alert rule, including the name and description, and click on "Create"

