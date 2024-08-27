# Cloud Security Solution
#### COSC 55: Security and Privacy | Owen Akel and Warren Klein

## Data in Transit Encryption via Secured Hyper Text Transfer Protocol (HTTPS)
* **Objective:** For our COSC55: Security and Privacy Final Project, Warren and I were tasked with brainstorming, designing and implementing a cloud security solution which is deployed through the AWS Learner Lab. The project took place over the last four weeks of the course and was divided into four distinct milestones:
	* `Milestone 1`: Research and Project Site — involved creating a project site, as well as idenifying an element of cloud security that we will research
	* `Milestone 2`: System Design — involved designing a cloud computing environment for an example organization, as well as creating a plan to deploy said cloud infrastructure
	* `Milestone 3`: System Implementation — involved deploying the cloud infrastructure specified in `Milestone 2`
	* `Milestone 4`: Cloud Security Solution — involved implementing the cloud security solution specified in `Milestone 1` within the cloud infrastructure deployed in `Milestone 3`
* **Proposed Security Solution:** Our proposed solution involved designing and deploying a secure, scalable cloud environment on Amazon Web Services (AWS). This environment was structured to isolate different departments within a Virtual Private Cloud (VPC), each with its dedicated subnet and EC2 instance. The project incorporates industry-standard practices such as traffic management through an Application Load Balancer (ALB), secure communication with SSL/TLS encryption, and domain management via GoDaddy.

## Project Infrastructure (see project tracker for more detail)
* **VPC and Subnets**: The project creates a VPC with four subnets, each dedicated to a specific department (Engineering, HR, IT, and Sales). Each subnet is placed in a different availability zone to ensure high availability.
* **Internet Gateway (IGW)**: An IGW is attached to the VPC to allow internet access.
* **Routing Table**: A routing table is configured to route traffic between the subnets and the internet via the IGW.
* **EC2 Instances**: Five EC2 instances are created, each assigned to its respective subnet and configured with Ubuntu t2.small.
* **Domain Registration**: A domain is registered via GoDaddy, which serves as the central access point for all department portals.
* **Wildcard SSL/TLS Certificate**: A wildcard certificate is obtained and applied to secure all subdomains under the main domain.
* **Application Load Balancer (ALB)**: An ALB is configured to manage traffic and distribute it to the appropriate department based on subdomain routing.
* **Subdomain Configuration**: Subdomains are created and linked to respective EC2 instances through the ALB using CNAME records in GoDaddy.
* **Login System**: A central login page is developed to authenticate users and redirect them to their respective department's portal.

## Setup and Configuration (see project tracker for more detail)

### Step 1: Create VPC and Subnets
1. Create a VPC with five subnets, each in a different availability zone:
   * Engineering Subnet
   * Sales Subnet
   * IT Subnet
   * HR Subnet
   * Home Subnet (for login portal)

### Step 2: Launch EC2 Instances
2. Launch an Ubuntu t2.small EC2 instance in each subnet.

### Step 3: Configure Internet Gateway (IGW) and Route Tables
3. Create an IGW to allow internet access.
4. Set up route tables to connect subnets and route traffic through the IGW.

### Step 4: Domain Setup with GoDaddy
4. Register a domain through GoDaddy.
5. Create subdomains for each department (e.g., `engineering.warrenkleinowenakelcosc55.com`).

### Step 5: Application Load Balancer and SSL/TLS
6. Set up an ALB, ensuring it operates within the VPC.
7. Apply a wildcard SSL/TLS certificate for secure communication.

### Step 6: Configure PHP and MySQL for Authentication
8. Develop a PHP script that authenticates users via MySQL and redirects them to their departmental pages.

### Step 7: Verification
9. Verify that the environment is functioning correctly by accessing the subdomains and ensuring traffic is properly routed and secured.

## Conclusion and Possible Next Steps
* This project provides a secure, scalable, and isolated environment for different departments within a hypothetical organization. It leverages a range of AWS services such as AWS Virtural Private Cloud (VPC), AWS Elastic Compute Cloud (EC2), AWS Certificate Manager, and AWS Application Load Balancer (ALB). The infrastructure supports secure access and independent operations for each department, with a central login system to streamline user access.
* In terms of next steps, the infrastructure for each department (Engineering, Sales, Information Technology, and Human Resources) could be built out. In addition, secure communciation channels between these departments could be developed in order to facilitate collaboration within the orgization. The UI/UX could also be further developed by leveraging front-end developer languages and tools such as HTML, CSS, JavaScript, or React to enhance the employee experience.

## Resources
* [AWS Documentation](https://docs.aws.amazon.com/)
* [GoDaddy SSL/TLS Setup Guide](https://medium.com/@samuelnnanna71/a-guide-to-obtaining-a-public-ssl-certificate-for-your-godaddy-domain-b6869c50f625)
* [Load Balancer Configuration](https://montanawong.medium.com/how-to-point-your-custom-domain-to-an-aws-load-balancer-51dc2eb6d84c)
* [Video Demonstration](https://drive.google.com/file/d/1rqTRogNbPhHJdHp7OnDiwT76MguqLSmK/view?usp=drive_link)
