# Azure Fundamentals: Implementing Network Security Groups (NSGs)

## Introduction

In this project, you'll learn how to secure Azure Virtual Machines (VMs) using Network Security Groups (NSGs). NSGs are used to control inbound and outbound traffic to your Azure resources. We'll cover setting up an Azure VM, configuring NSGs, and applying best practices for securing your Azure environment.

## Pre-requisites

- Basic understanding of cloud computing
- An Azure account (free trial available)
- Basic knowledge of command-line interface (CLI)

## Lab Set-up and Tools

1. **Azure Account**: Sign up for a free Azure account if you don't have one.
2. **Azure Portal**: Access to the Azure Management Portal.
3. **Azure CLI**: Install the Azure Command Line Interface (CLI) on your local machine.

## Exercises

### Exercise 1: Create a Virtual Network and Subnet

#### Steps

1. Log in to the [Azure Portal](https://portal.azure.com/).
2. Navigate to "Create a resource" and select "Virtual Network".
3. Configure the virtual network:
    - Name: `myVNet`
    - Address space: `10.0.0.0/16`
    - Subnet name: `mySubnet`
    - Subnet address range: `10.0.1.0/24`
4. Review and create the virtual network.

#### Expected Output

- A virtual network `myVNet` with a subnet `mySubnet` created.

### Exercise 2: Launch an Azure Virtual Machine

#### Steps

1. Navigate to "Create a resource" and select "Virtual Machine".
2. Configure the VM:
    - Name: `myVM`
    - Region: Select a region
    - Image: Windows Server 2019 Datacenter
    - Size: B1s (Basic)
    - Authentication type: Password
    - Username: `azureuser`
    - Password: Choose a strong password
    - Select the previously created virtual network `myVNet` and subnet `mySubnet`
3. Review and create the virtual machine.

#### Expected Output

- An Azure VM `myVM` running in the `myVNet` virtual network.

### Exercise 3: Create a Network Security Group (NSG)

#### Steps

1. Navigate to "Create a resource" and select "Network Security Group".
2. Configure the NSG:
    - Name: `myNSG`
    - Region: Same as the VM region
3. Review and create the NSG.

#### Expected Output

- An NSG `myNSG` created.

### Exercise 4: Configure Inbound and Outbound Security Rules

#### Steps

1. Navigate to the newly created NSG `myNSG`.
2. Under "Settings", click on "Inbound security rules".
3. Add an inbound rule to allow RDP (port 3389) from your IP address:
    - Source: IP Addresses
    - Source IP address: Your IP address
    - Destination: Any
    - Destination port ranges: 3389
    - Protocol: TCP
    - Action: Allow
    - Priority: 1000
    - Name: `Allow-RDP`
4. Under "Settings", click on "Outbound security rules".
5. Ensure the default outbound rule allows all outbound traffic.

#### Expected Output

- NSG `myNSG` with an inbound rule allowing RDP access from your IP address.

### Exercise 5: Associate NSG with the VM's Network Interface

#### Steps

1. Navigate to the "Network interfaces" section in the Azure Portal.
2. Select the network interface associated with `myVM`.
3. Under "Settings", click on "Network security group".
4. Associate the network interface with the NSG `myNSG`.

#### Expected Output

- The network interface of `myVM` is now secured by `myNSG`.

## Conclusion

By completing these exercises, you have successfully set up an Azure VM, created a Network Security Group, configured security rules, and associated the NSG with your VM. These skills are essential for securing Azure resources and managing network traffic effectively.
