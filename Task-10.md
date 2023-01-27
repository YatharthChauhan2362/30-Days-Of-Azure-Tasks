# 1. Create a Vnet with single subnet and Create a VM.

To create a virtual network (VNet) with a single subnet and a virtual machine (VM) in Azure, you can use Azure PowerShell or Azure CLI.

Here is an example of how to do this using Azure PowerShell:

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

You can also use Azure CLI:

    az group create --name MyResourceGroup --location eastus    
    az network vnet create --name MyVNet --resource-group MyResourceGroup --address-prefix 10.0.0.0/16
    az network vnet subnet create --name MySubnet --resource-group MyResourceGroup --vnet-name MyVNet --address-prefix 10.0.0.0/24
    az vm create --name MyVM --resource-group MyResourceGroup --location eastus --vnet-name MyVNet --subnet MySubnet

Please make sure you have the latest Azure PowerShell and Azure CLI version installed on your machine, also Azure subscription and necessary permissions are required.



# 2. Schedule a Daily backup of VM at 3:AM using vault

To schedule a daily backup of a virtual machine (VM) at 3:00 AM using an Azure Backup vault, you can use Azure PowerShell or Azure CLI.

Using Azure PowerShell:

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

Using Azure CLI:

    az backup vault create --name MyBackupVault --resource-group MyResourceGroup --location eastus
    az backup protection enable-for-vm --vm-name MyVM --resource-group MyResourceGroup --vault-name MyBackupVault
    az backup policy create --name MyBackupPolicy --resource-group MyResourceGroup --vault-name MyBackupVault --workload-type AzureVM --frequency Daily --start-time "03:00"
    az backup protection set-policy --policy-name MyBackupPolicy --resource-group MyResourceGroup --vault-name MyBackupVault --vm MyVM

Please make sure you have the latest Azure PowerShell and Azure CLI version installed on your machine, also Azure subscription and necessary permissions are required.

Also, note that the above commands sets up the schedule and policy but it doesn't initiate the backup, you will need to use Start-AzRecoveryServicesBackup or az backup protection backup to initiate the first backup.


# 3. Create an Alert rule for VM CPU percentage.

# 4. Criteria: CPU% More Than 80%, There Should be an alert on email.
