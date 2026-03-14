# Azure-Documents

# Step 1: Start the Creation Process
Log in to the Azure Portal.

In the search bar at the top, type "Virtual Machines" and select it.

Click + Create and select Azure virtual machine.

Step 2: Configure the Basics
This is the most important tab. You define the identity and power of your VM here.

Project Details: * Subscription: Choose your active subscription (e.g., Free Trial).

Resource Group: Click Create new and name it Lab-RG.

Instance Details:

VM Name: MyFirstVM.

Region: Choose the one closest to you (e.g., East US).

Availability options: Select No infrastructure redundancy required for a simple lab.

Security type: Keep as Standard (or Trusted Launch for 2026 defaults).

Image: Select Ubuntu Server 24.04 LTS - Gen 2.

Size: Look for Standard_B1s (it’s the most cost-effective for labs).

Step 3: Administrator Account
Choose how you want to log in.

Authentication type: Select SSH public key (More secure).

Username: azureuser.

Key pair name: MyFirstVM_key.

Step 4: Inbound Port Rules
To talk to your VM, you must open a "door."

Public inbound ports: Select Allow selected ports.

Select inbound ports: Choose SSH (22).

Step 5: Networking (The "House")
Click Next: Disks (keep defaults), then Next: Networking.

Azure will automatically suggest a new Virtual Network (VNet) and Subnet.

Public IP: Ensure one is being created so you can access it from your home computer.

NIC network security group: Select Basic.

Step 6: Review + Create
Click Review + create at the bottom. Azure will run a "Validation" to make sure your settings are valid.

Once it says Validation Passed, click Create.

IMPORTANT: A popup will appear asking to Download private key. Click it and save the .pem file safely. You cannot download it again!

Step 7: Connect to your VM
Once the deployment is complete:

Click Go to resource.
### 1. [Create and manage Azure Vnet - Portal](https://docs.microsoft.com/en-us/azure/virtual-network/quick-create-portal)

Copy the Public IP address from the Overview page.

Open your terminal (Command Prompt or PowerShell) and type:

Bash
ssh -i path/to/your/key.pem azureuser@<Your-Public-IP>
