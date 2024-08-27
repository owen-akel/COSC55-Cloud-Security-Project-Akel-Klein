# Cloud Security Solution
#### COSC 55: Security and Privacy | Owen Akel and Warren Klein

## Data in Transit Encryption via Secured Hyper Text Transfer Protocol (HTTPS)
* **Objective:** For our COSC55: Security and Privacy Final Project, Warren and I were tasked with brainstorming, designing and implementing a cloud security solution which is deployed through the AWS Learner Lab. The project took place over the last four weeks of the course and was divided into four distinct milestones:
	* `Milestone 1`: Research and Project Site — involved creating a project site, as well as idenifying an element of cloud security that we will research
	* `Milestone 2`: System Design — involved designing a cloud computing environment for an example organization, as well as creating a plan to deploy said cloud infrastructure
	* `Milestone 3`: System Implementation — involved deploying the cloud infrastructure specified in `Milestone 2`
	* `Milestone 4`: Cloud Security Solution — involved implementing the cloud security solution specified in `Milestone 1` within the cloud infrastructure deployed in `Milestone 3`
* **Proposed Security Solution:** Our proposed solution involved designing and deploying a secure, scalable cloud environment on Amazon Web Services (AWS). This environment was structured to isolate different departments within a Virtual Private Cloud (VPC), each with its dedicated subnet and EC2 instance. The project incorporates industry-standard practices such as traffic management through an Application Load Balancer (ALB), secure communication with SSL/TLS encryption, and domain management via GoDaddy.

## Detailed Project Infrastructure
* **VPC and Subnets**: The project creates a VPC with four subnets, each dedicated to a specific department (Engineering, HR, IT, and Sales). Each subnet is placed in a different availability zone to ensure high availability.
* **Internet Gateway (IGW)**: An IGW is attached to the VPC to allow internet access.
* **Routing Table**: A routing table is configured to route traffic between the subnets and the internet via the IGW.
* **EC2 Instances**: Five EC2 instances are created, each assigned to its respective subnet and configured with Ubuntu t2.small.
* **Domain Registration**: A domain is registered via GoDaddy, which serves as the central access point for all department portals.
* **Wildcard SSL/TLS Certificate**: A wildcard certificate is obtained and applied to secure all subdomains under the main domain.
* **Application Load Balancer (ALB)**: An ALB is configured to manage traffic and distribute it to the appropriate department based on subdomain routing.
* **Subdomain Configuration**: Subdomains are created and linked to respective EC2 instances through the ALB using CNAME records in GoDaddy.
* **Login System**: A central login page is developed to authenticate users and redirect them to their respective department's portal.

## Resources
* [AWS Documentation](https://docs.aws.amazon.com/)
* [GoDaddy SSL/TLS Setup Guide](https://medium.com/@samuelnnanna71/a-guide-to-obtaining-a-public-ssl-certificate-for-your-godaddy-domain-b6869c50f625)
* [Load Balancer Configuration](https://montanawong.medium.com/how-to-point-your-custom-domain-to-an-aws-load-balancer-51dc2eb6d84c)
* [Video Demonstration](https://drive.google.com/file/d/1rqTRogNbPhHJdHp7OnDiwT76MguqLSmK/view?usp=drive_link)
