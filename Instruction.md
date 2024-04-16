# Installing Python 3, python3-pip, and Streamlit on AWS EC2 Instance

This guide provides step-by-step instructions to install Python 3, `python3-pip`, and Streamlit on an AWS EC2 instance and modify the inbound rules of the associated security group to allow traffic on port 8501.

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Connect to EC2 Instance](#connect-to-ec2-instance)
3. [Install Python 3 and python3-pip](#install-python-3-and-python3-pip)
4. [Install Streamlit](#install-streamlit)
5. [Modify Security Group Inbound Rules](#modify-security-group-inbound-rules)

---

## Prerequisites

- AWS account
- AWS EC2 instance running
- AWS CLI installed (optional but recommended)

---

## Connect to EC2 Instance

### Using SSH

You can connect to your EC2 instance using SSH. Replace `your-ec2-instance-ip` with your actual EC2 instance IP address.

```bash
ssh -i "your-key.pem" ec2-user@your-ec2-instance-ip
```
Using AWS Management Console
Alternatively, you can connect using the AWS Management Console:

Log in to the AWS Management Console.
Navigate to the EC2 dashboard.
Select your EC2 instance.
Click on the Connect button to get connection details.

## Install Python 3 and python3-pip
Once connected to your EC2 instance, run the following commands to install Python 3 and python3-pip.

```
sudo yum update -y
sudo yum install python3 -y
sudo yum install python3-pip -y
```

## Install Streamlit
Install Streamlit using pip.

```
pip3 install streamlit
```

## Modify Security Group Inbound Rules
To modify the inbound rules of your EC2 instance's security group to allow traffic on port 8501, follow these steps:

- Log in to the AWS Management Console.
- Navigate to the EC2 dashboard.
- In the navigation pane, click on Security Groups.
- Select the security group associated with your EC2 instance.
- Click on the Inbound rules tab.
- Click on Edit inbound rules.
- Add a new rule with the following settings:
- Type: Custom TCP
- Protocol: TCP
- Port Range: 8501
- Source: Anywhere (0.0.0.0/0, ::/0)
- Click Save rules.
