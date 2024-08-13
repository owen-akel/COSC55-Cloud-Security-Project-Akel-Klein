## Project Milestone 2
### Summary of Tasks:
The below list will outline a step-by-step process to deploy a secure cloud environment using AWS to accomplish the project goals outlined in Project Milestone 1. To reiterate the goal of the project, Warren and I are interested in exploring data encrypton in transit. Our plan leverages GPG excryption to encrypt and decrypt in-transit and at-rest data. 

### Task List:
* Task 1: Set up Virtual Private Cloud (VPC) and Subnets for each department
	* Create VPC
	* Create Subnets for Engineering, Sales, IT, and HR departments
	* Attatch Internet Gateway
	* Update Route Tables and associate Route Tables with all subnets
* Task 2: Launch EC2 Instances
	* Launch Engineering Server (Ubuntu Web Server)
	* Launch Sales Server (Windows CRM Server)
	* Launch IT Server (RedHat File Server)
	* Launch HR Server (Ubuntu Intranet Server)
* Task 3: Set Up AWS Certificate Manager for HTTPS
	* Request SSL/TLS certificates
	* Attatch certificates
* Task 4: Implement PGP Encryption for Data at Rest and In Transit
	* Install PGP Software using either GnuPG (Ubuntu/RedHat Servers) or Gpg4win (Windows Server)
	* Generate PGP Keys, excrypt sensitive data, and decrypt sensitive data using GnuPG/Gpg4win on appropriate servers
* Task 5: Configure Networking and Security
	* Configure security groups, ensuring only necessary ports are open and restricting SSH and RDP access to only our IP address
	* Ensure route tables are correctly associated with each subnet and confirm only necessary traffic is routed through the Internet Gateway
* Task 6: Set Up Monitoring and Logging with AWS CloudWatch
	* Enable CloudWatch Monitoring
	* Set up CloudWatch Alarms
	* Enable Logging
