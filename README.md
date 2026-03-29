AWS Networking Assignment
Overview

This project shows how to build a secure AWS network using a VPC, public and private subnets, an Internet Gateway, and a NAT Gateway.

VPC
Name: my-vpc
CIDR: 10.0.0.0/16

Subnets
Public Subnet: 10.0.1.0/24 (eu-north-1a)
Private Subnet: 10.0.2.0/24 (eu-north-1b)

Internet Gateway
Attached to the VPC
Provides internet access to the public subnet

NAT Gateway
Created in the public subnet
Allows private subnet instances to access the internet

Route Tables

Public Route Table:
10.0.0.0/16 → local
0.0.0.0/0 → Internet Gateway

Private Route Table:
10.0.0.0/16 → local
0.0.0.0/0 → NAT Gateway

EC2 Instances
Public EC2 (Bastion):
Has public IP
Used to connect to private EC2

Private EC2:
No public IP
Only accessible from public EC2

Security Groups
Public EC2:
SSH (port 22) from anywhere
Private EC2:
SSH (port 22) only from public EC2

Access Flow
Laptop → Public EC2 → Private EC2

NAT Test
Command:
curl http://example.com

Output:
Example Domain
This confirms that the private EC2 can access the internet through the NAT Gateway.

Screenshots
The following screenshots are included:
AWS DAIGRAM
VPC setup
Subnets
Route tables
NAT Gateway
EC2 instances
Security groups
Terminal output

Conclusion:
This setup demonstrates a secure AWS network with proper isolation, routing, and controlled access using a NAT Gateway.
