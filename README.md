# Azure Resource Group Deployment

<p align="center">
<img src="images/AzureImage.png" width="500"/>
</p>

## Project Overview

This project demonstrates how to create a **Resource Group in Microsoft Azure**. Resource Groups act as containers that organize and manage related Azure resources such as **Virtual Machines, storage accounts, networking components, and other services**.

In this walkthrough, we will:

- Create a free Microsoft Azure account
- Access the Azure Portal
- Locate the Resource Groups service
- Create a new Resource Group
- Verify the Resource Group deployment
- Create a Windows Virtual Machine within the Resource Group
- Access the Virtual Machine using Remote Desktop Protocol (RDP)

---

# Demonstration

## Step 1 – Create a Free Microsoft Azure Account

Before deploying any cloud resources, you must first create a **Microsoft Azure account**.

Visit the official Microsoft Azure website below:

**Azure Free Account:**  
https://azure.microsoft.com/free/

Follow the instructions to:

- Sign in with a Microsoft account or create one
- Verify your identity
- Complete the free account registration

After the account is created, log in to the **Azure Portal**.

---

## Step 2 – Search for Resource Groups in Azure

After logging into the **Azure Portal**, locate the **search bar at the top of the page**.

Type **Resource Groups** into the search bar.

From the search results, select **Resource Groups**.

![Searching Resource Groups](images/01-resource-groups-search.png)

---

## Step 3 – Open the Resource Groups Dashboard

The **Resource Groups dashboard** will now open.

This page displays all Resource Groups associated with your Azure subscription. If this is a new account, the page will show that **no resource groups currently exist**.

Click the **Create** button to start creating a new Resource Group.

![Resource Groups Dashboard](images/02-resource-groups-search.png)

---

## Step 4 – Configure the Resource Group

The **Create a Resource Group** configuration page will now appear.

Enter the following settings:

**Subscription:** Azure subscription 1  
**Resource Group Name:** osTicket  
**Region:** Central US

After entering the information, click **Review + Create**.

![Resource Group Configuration](images/03-resource-groups-search.png)

---

## Step 5 – Review the Resource Group Settings

Azure will display a **Review + Create** page showing the configuration details.

Confirm that the following settings are correct:

- Subscription
- Resource Group Name
- Region

Once verified, click **Create** to deploy the Resource Group.

![Review Resource Group](images/04-resource-groups-search.png)

---

## Step 6 – Verify the Resource Group Deployment

After the deployment process completes, return to the **Resource Groups dashboard**.

You should now see the newly created Resource Group listed.

In this example, the **osTicket Resource Group** has been successfully created and is ready to host Azure resources.

![Resource Group Created](images/05-resource-groups-search.png)

---
---

# Creating an Azure Virtual Machine

After creating the Resource Group, the next step is to deploy a **Virtual Machine (VM)** inside that Resource Group. Virtual Machines allow you to run operating systems and applications in the cloud just like a physical computer.

---

## Step 7 – Search for Virtual Machines

At the top of the Azure Portal, locate the **search bar**.

Type **Virtual Machines** into the search field.

From the results list, select **Virtual Machines**.

![Search Virtual Machines](images/06-resource-groups-search.png)

---

## Step 8 – Open the Virtual Machines Dashboard

The **Virtual Machines dashboard** will now open.

If no virtual machines have been created yet, the page will display **No virtual machines to display**.

Click the **Create** button to begin creating a new virtual machine.

![Virtual Machine Dashboard](images/07-resource-groups-search.png)

---

## Step 9 – Select Virtual Machine Deployment

After clicking **Create**, a dropdown menu will appear with several options.

Select **Virtual Machine** to begin the virtual machine deployment process.

![Select Virtual Machine](images/08-resource-groups-search.png)

---

## Step 10 – Select the Resource Group

The **Create a Virtual Machine** configuration page will open.

Under **Project Details**, locate the **Resource Group** field.

Select the previously created Resource Group named **osTicket**.

This ensures the virtual machine will be organized inside the correct resource container.

![Select Resource Group](images/09-resource-groups-search.png)

---

## Step 11 – Configure Virtual Machine Basics

Next, configure the **Instance Details** for the virtual machine.

Enter the following information:

**Virtual Machine Name:** osTicket-Proj  
**Region:** Central US

These settings determine the name of the machine and the geographic region where it will be deployed.

![VM Basic Configuration](images/10-resource-groups-search.png)

---

## Step 12 – Configure Availability and VM Size

Continue configuring the virtual machine settings.

Set the following options:

**Availability Options:** Availability zone  
**Zone Options:** Self-selected zone  
**Availability Zone:** Zone 1

For the virtual machine size, select:

**Size:** Standard_D2s_v3  
(2 vCPUs, 8 GB RAM)

This size provides enough resources for the project while keeping costs relatively low. 
Cost to the right is only if the VM is running the entire month.
We will only be using the VM for a limited time.

![VM Size and Availability](images/11-resource-groups-search.png)

---

---

# Step 13 – Select the Virtual Machine Image

Under **Image**, click the dropdown menu to view available operating systems.

From the list of available images, select:

**Windows 11 Pro, version 25H2 – x64 Gen2**

This image will install Windows 11 on the virtual machine.

![Select VM Image](images/12-resource-groups-search.png)

---

# Step 14 – Select the Virtual Machine Size

Next, locate the **Size** option.

Click the dropdown menu and select:

**Standard_D2s_v3 – 2 vCPUs, 8 GiB Memory**

This VM size provides enough computing resources to run the project while keeping costs manageable.

![Select VM Size](images/13-resource-groups-search.png)

---

# Step 15 – Configure Administrator Credentials

Under **Administrator account**, create login credentials for the virtual machine.

Enter the following:

**Username:** Create a username of your choice  
**Password:** Create a secure password  
**Confirm Password:** Re-enter the same password

These credentials will later be used to log into the virtual machine using Remote Desktop.

![Create Administrator Account](images/14-resource-groups-search.png)

---

# Step 16 – Configure Licensing and Ports

Scroll down to the **Licensing** section.

Check the box confirming that you have an eligible Windows license:

✔ **I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights**

Under **Public inbound ports**, ensure the following option is selected:

**Allow selected ports**

For **Select inbound ports**, choose:

**RDP (3389)**

This allows the virtual machine to be accessed using Remote Desktop.

Click **Next: Disks** to continue.

![Configure Licensing and Ports](images/15-resource-groups-search.png)

---

# Step 17 – Configure Disk Settings

The **Disks** tab controls the storage used by the virtual machine.

Leave the default settings as they are:

**OS Disk Size:** Image default (127 GiB)  
**OS Disk Type:** Premium SSD

After confirming the settings, click **Next: Networking**.

![Configure Disks](images/16-resource-groups-search.png)

---

# Step 18 – Configure Networking

The **Networking** tab configures how the virtual machine connects to the internet.

Confirm the following default settings:

**Virtual Network:** (new) osTicket-Proj-vnet  
**Subnet:** default (10.0.0.0/24)  
**Public IP:** (new) osTicket-Proj-ip

Ensure **Public inbound ports** is set to:

**Allow selected ports**

And verify **RDP (3389)** is selected.

Once everything is confirmed, click **Review + create**.

![Configure Networking](images/17-resource-groups-search.png)

---

# Step 19 – Create the Virtual Machine

After reviewing all configuration settings, scroll to the bottom of the page.

Click the **Create** button to begin deploying the virtual machine.

Azure will now begin provisioning the virtual machine and all required resources.

![Create Virtual Machine](images/18-resource-groups-search.png)

---

# Step 20 – Deployment in Progress

After clicking **Create**, Azure will begin the deployment process.

A deployment screen will appear showing that the virtual machine and supporting resources are being created.

During this process Azure automatically creates resources such as:

- Virtual Network
- Network Security Group
- Public IP Address

This process may take several minutes to complete.

![Deployment in Progress](images/19-resource-groups-search.png)

---

# Step 21 – Deployment Complete

Once Azure finishes creating the resources, the deployment page will display a message stating:

**Your deployment is complete**

This confirms that the virtual machine has been successfully created and is ready to use.

From this page you can click **Go to resource** to view the virtual machine.

![Deployment Complete](images/20-resource-groups-search.png)

---

# Step 22 – Verify the Virtual Machine

To verify the virtual machine exists, return to the Azure search bar at the top of the portal.

Type **Virtual Machines** into the search field.

Select **Virtual Machines** from the results list.

This will open the Virtual Machines dashboard where you can view and manage the virtual machine that was just created.

![Search Virtual Machines Again](images/21-resource-groups-search.png)

---

