# AWS-VPC-Peering-Project
AWS VPC peering project demonstrating private connectivity, EC2 instances, route tables, security groups, and SSH access through a bastion host

Project Overview

This project demonstrates how to establish private network connectivity between two Amazon Virtual Private Clouds (VPCs) using AWS VPC Peering. It uses EC2 instances, route tables, security groups, and a bastion host to securely communicate between private instances.

Objectives

- Create and configure two separate VPCs.
- Configure public and private subnets.
- Launch EC2 instances in the required subnets.
- Establish a VPC peering connection between the two VPCs.
- Configure route tables to enable private communication.
- Apply security group rules to control network traffic.
- Access private EC2 instances through a bastion host.
- Test connectivity using private IP addresses and ping.
- Document troubleshooting, results, and cleanup procedures.

AWS Architecture

The project consists of two VPCs:

VPC A — "ewb-vpc-a"

- CIDR block: "10.10.0.0/16"
- Public subnet: "10.10.1.0/24"
- Private subnet: "10.10.2.0/24"
- Bastion host: "10.10.1.10"
- App-A instance: "10.10.2.10"
- Internet Gateway: "ewb-igw-a"

VPC B — "ewb-vpc-b"

- CIDR block: "10.20.0.0/16"
- Private subnet: "10.20.1.0/24"
- App-B instance: "10.20.1.10"
- No public IP address is assigned to App-B.

VPC Peering Connection

- Name: "ewb-a-b-peer"
- Connects VPC A and VPC B.
- Route tables direct traffic for the remote VPC through the peering connection.

AWS Services Used

- Amazon Virtual Private Cloud (VPC)
- Amazon EC2
- VPC Peering
- Subnets
- Route Tables
- Internet Gateway
- Security Groups
- SSH
- ICMP/Ping

Implementation Steps

1. Created VPC A and VPC B with separate CIDR blocks.
2. Created the required public and private subnets.
3. Configured the Internet Gateway for VPC A.
4. Launched the bastion host, App-A, and App-B EC2 instances.
5. Configured security groups to control SSH and ICMP traffic.
6. Created and accepted the VPC peering connection.
7. Added routes to the relevant route tables.
8. Connected to private instances through the bastion host.
9. Tested communication between App-A and App-B using their private IP addresses.
10. Documented connectivity testing, troubleshooting, and cleanup steps.

Connectivity Testing

The following tests were performed during the project:

Test| Expected/Observed Result
App-A to App-B ping| Successful; 0% packet loss in the recorded successful test
App-B to App-A ping| Successful; 0% packet loss in the recorded successful test
SSH access to App-B through the bastion host| Successful
Connectivity troubleshooting| Both ping failure and recovery were observed

The successful ping tests confirmed private IP connectivity between the two VPCs at the time of testing.

Project Results

- Established VPC peering between two VPCs.
- Configured routes for communication between private subnets.
- Used security groups to control network access.
- Accessed a private EC2 instance through a bastion host.
- Verified connectivity using ping and SSH.
- Documented troubleshooting and project verification.

Lessons Learned

- VPC peering enables private communication between VPCs with non-overlapping CIDR blocks.
- Route tables must contain the correct routes for traffic to reach the peered VPC.
- Security group rules must permit the required traffic.
- Private instances can be accessed through a properly configured bastion host.
- Testing and troubleshooting help identify connectivity issues.

Project Documentation

The repository may include:

- "README.md" — Project overview and instructions.
- "YourName_EWB_VPC_Peering.pdf" — Final project report.
- "screenshots/" — Evidence of AWS configuration and connectivity tests.
- "architecture/" — Network architecture diagram, if available.

Security Notes

- Do not upload private SSH keys, passwords, AWS access keys, secret keys, or session tokens.
- Review screenshots and reports before making the repository public.
- Use a private repository if the project contains information that should not be shared publicly.
- Verify that AWS resources have been cleaned up before considering the project complete.

Conclusion

This project provided practical experience with AWS networking, VPC peering, EC2 instances, route tables, security groups, bastion-host access, and connectivity testing. It demonstrates how private communication can be configured between separate VPCs using AWS networking services.

Author

Shaik Shareef

Project: AWS VPC Peering
Program: EWB Cloud Labs — AWS Student Project
