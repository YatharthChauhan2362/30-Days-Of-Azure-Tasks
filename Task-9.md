# TASK-9

# 1. Creating a Snapshot of the VM & creating VM from VHD

A snapshot is a read-only copy of a virtual hard disk (VHD) that can be used to create a new virtual machine or to restore an existing one. 
- Snapshots can be taken of both managed and unmanaged disks, and can be used to revert a disk to a previous state in case of data loss or corruption. 
- Snapshots can also be used for backup and disaster recovery purposes, as well as for testing and development. 
- They are stored as blobs in an Azure storage account, and can be managed through Azure Portal, Azure PowerShell, Azure CLI, or Azure SDKs.

To create a snapshot of a VM in Azure and then create a new VM from the snapshot, you can follow these steps:

1.	Sign in to the Azure portal (https://portal.azure.com/)
2.	Navigate to the VM that you want to create a snapshot of
3.	Click on the "Create Snapshot" button in the "Overview" section of the VM
4.	Provide a name and description for the snapshot, and select the storage account where you want to store the snapshot
5.	Click the "Create" button to start the snapshot creation process

Once the snapshot is created, you can use it to create a new VM. Here are the steps:

1.	Go to the Azure portal, select "Create a resource"
2.	Select "Windows Server" or "Linux" depending on the OS of the original VM
3.	Select "From image" in the "Basics" tab
4.	Select the snapshot that you created earlier and continue with the VM creation process
5.	Provide a name and size for the new VM
6.	Select the options like vnet,subnet,availability set etc.
7.	Finally click on create to launch the new VM.
Alternatively, You can also create a new VM from the snapshot by creating a VHD from the snapshot and then create a new VM from the VHD.
1.	Go to the Azure portal, select the storage account where the snapshot is stored
2.	Select "Containers" and then select the container where the snapshot is stored
3.	Select the snapshot and then click on "Create" button
4.	Select "VHD" and provide a name for the VHD
5.	Once the VHD is created, you can then use it to create a new VM by following the steps above.


### Tutorial Link:

[Creating a Snapshot of the VM & creating VM from VHD](https://www.youtube.com/watch?v=F5l7a5u3G1Q&ab_channel=HowAzureWorks)

