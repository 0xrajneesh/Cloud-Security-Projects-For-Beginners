# Introduction to Cloud Security: Securing AWS EC2 Instances

## Introduction

In this project, you'll learn how to secure AWS EC2 instances. We'll cover basic concepts like setting up security groups, configuring key pairs for SSH access, and implementing best practices for securing EC2 instances.

## Pre-requisites

- Basic understanding of cloud computing
- An AWS account (free tier available)
- Basic knowledge of command-line interface (CLI)

## Lab Set-up and Tools

1. **AWS Account**: Sign up for a free AWS account if you don't have one.
2. **AWS Management Console**: Access to the AWS Management Console.
3. **AWS CLI**: Install the AWS Command Line Interface (CLI) on your local machine.
4. **SSH Client**: Install an SSH client (e.g., OpenSSH, PuTTY) on your local machine.

## Exercises

### Exercise 1: Launch an EC2 Instance

#### Steps

1. Log in to the [AWS Management Console](https://aws.amazon.com/console/).
2. Navigate to the EC2 Dashboard.
3. Click on "Launch Instance".
4. Choose an Amazon Machine Image (AMI) (e.g., Amazon Linux 2 AMI).
5. Select an instance type (e.g., t2.micro which is free tier eligible).
6. Configure instance details (leave default settings).
7. Add storage (leave default settings).
8. Add tags (optional).
9. Configure Security Group:
    - Create a new security group.
    - Add a rule to allow SSH (port 22) from your IP.
10. Review and launch the instance.
11. Select "Create a new key pair", name it, and download the key pair.
12. Launch the instance.

#### Expected Output

- An EC2 instance running and accessible via SSH.

### Exercise 2: Connect to Your EC2 Instance

#### Steps

1. Open your terminal or SSH client.
2. Navigate to the directory where your key pair is stored.
3. Change the permissions of your key pair file:
    ```bash
    chmod 400 your-key-pair.pem
    ```
4. Connect to your instance using the public DNS:
    ```bash
    ssh -i "your-key-pair.pem" ec2-user@your-instance-public-dns
    ```

#### Expected Output

- Successful SSH connection to your EC2 instance.

### Exercise 3: Update and Secure Your Instance

#### Steps

1. Update the package list:
    ```bash
    sudo yum update -y
    ```
2. Install security updates:
    ```bash
    sudo yum upgrade -y
    ```
3. Create a new user:
    ```bash
    sudo adduser newuser
    ```
4. Grant new user sudo privileges:
    ```bash
    sudo usermod -aG wheel newuser
    ```
5. Secure SSH access:
    - Edit the SSH configuration file:
        ```bash
        sudo vi /etc/ssh/sshd_config
        ```
    - Disable root login:
        ```plaintext
        PermitRootLogin no
        ```
    - Allow only key-based authentication:
        ```plaintext
        PasswordAuthentication no
        ```
    - Restart the SSH service:
        ```bash
        sudo systemctl restart sshd
        ```

#### Expected Output

- Instance updated and secured, root login disabled, and only key-based authentication allowed.

### Exercise 4: Configure a Basic Firewall with Security Groups

#### Steps

1. In the AWS Management Console, navigate to the EC2 Dashboard.
2. Select your instance and go to the "Security" tab.
3. Click on the security group associated with your instance.
4. Edit the inbound rules:
    - Remove the SSH rule allowing access from anywhere.
    - Add an SSH rule allowing access only from your IP address.
5. Edit the outbound rules (if necessary).

#### Expected Output

- A security group configured to restrict SSH access to your IP only.

### Exercise 5: Set Up CloudWatch for Monitoring

#### Steps

1. In the AWS Management Console, navigate to the CloudWatch Dashboard.
2. Click on "Alarms" and then "Create Alarm".
3. Select the "EC2" metric and choose your instance.
4. Configure the alarm (e.g., CPU utilization > 80% for 5 minutes).
5. Set up notifications (e.g., via email).
6. Review and create the alarm.

#### Expected Output

- CloudWatch alarm set up to monitor your EC2 instance and notify you of high CPU utilization.

## Conclusion

By completing these exercises, you have successfully launched, connected to, secured, and monitored an AWS EC2 instance. These are essential skills for maintaining the security and performance of your cloud infrastructure.
