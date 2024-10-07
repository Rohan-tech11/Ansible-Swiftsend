# Ansible Deployment for SwiftSend

## Overview
This repository contains Ansible playbooks and roles for automating Jenkins deployment on Amazon EKS (Elastic Kubernetes Service) as part of the **SwiftSend** project. The automation is executed through an EC2 instance acting as a control node, utilizing AWS Systems Manager (SSM) for secure connection management.


## Key Features
* **Secure Automation**: 
  * Leverages AWS Systems Manager (SSM) for secure connection to EC2 control node
  * No direct SSH access required, enhancing security posture
  * All credentials and sensitive data managed through AWS SSM Parameter Store

* **EKS Integration**:
  * Direct interaction with EKS cluster using `kubectl` commands
  * Automated Jenkins deployment and configuration on Kubernetes
  * Scalable and maintainable infrastructure-as-code approach


## AWS SSM Configuration
The project uses AWS SSM for secure connection management. 
SSM Connection Details

Host: EC2 instance ID is used instead of IP address
Connection Type: AWS SSM (aws_ssm)
S3 Bucket: Dedicated bucket for SSM session logs
Region: ca-central-1






## Technologies Used
- **Ansible**: Configuration management and automation tool
- **AWS Services**:
  - AWS Systems Manager (SSM)
  - Elastic Kubernetes Service (EKS)
  - Elastic Compute Cloud (EC2)
- **Kubernetes**: Container orchestration platform
- **Jenkins**: Continuous Integration/Continuous Deployment server


## Usage
1. Ensure AWS credentials are configured:
   ```bash
   aws configure
   ```

2. Verify SSM connection to EC2:
   ```bash
   ansible ansible-ec2 -m ping
   ```

3. Run the Jenkins deployment playbook:
   ```bash
   ansible-playbook playbooks/install-jenkins.yml
   ```

## Security Considerations
- All connections are managed through AWS SSM, eliminating need for SSH key management
- EC2 instance requires appropriate IAM role with SSM permissions to  interact with EKS.




## License
[Add your license information here]

## Contact
email-id:mogaralarohan12345@gmail.com