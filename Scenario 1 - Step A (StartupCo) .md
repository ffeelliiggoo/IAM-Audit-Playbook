## Architecture Overview

The diagram below illustrates **StartupCo’s current AWS architecture**, including EC2, S3, RDS, and CloudWatch components.  
It highlights how resources are deployed across Development and Production environments, providing a baseline for identifying risks, technical debt, and IAM gaps.

<p align="center">
  <img src="https://raw.githubusercontent.com/ffeelliiggoo/IAM-Audit-Playbook/4fdf34b68d7d4c46f9a23f397650133d3c8316f5/StartupCo%20Current%20Architecture.png" 
       alt="StartupCo Current Architecture" width="800"/>
</p>

# Architecture First Look – Notes

## Project Brief
StartupCo is operating in a **single VPC with a single Availability Zone**, configured with both public and private subnets.  

- **Public Subnet:** Hosts the Application Load Balancer and EC2 web servers. Currently using **default security groups**, which is a major weakness. IAM permissions for developers and operations are not properly defined.  
- **Private Subnet:** Runs EC2 application instances and an RDS database. Default security groups do not enforce proper controls, leaving analyst access unmanaged.  
- **Consideration:** Create additional private subnets to segment EC2 and RDS for **isolation and least privilege**, ensuring each subnet serves a distinct purpose for stronger boundaries.  

---

## Shared Services
- **S3 buckets** – storing application data.  
- **CloudWatch** – monitoring and logging.  
- **IAM (currently misused):** All users rely on the **root account**. Permissions are not separated by roles or duties.  

---

## Security Issues Identified
- Use of a **shared root account** across the organization.  
- No MFA enabled; credentials are not securely managed.  
- Lack of role-based access controls (RBAC).  
- No dedicated IAM groups for different teams.  
- No password or MFA enforcement policies.  

---

## Task Priorities
1. Implement **proper IAM permissions** tied to least privilege.  
2. **Developers** – EC2 + S3 access.  
3. **Operations** – full infrastructure access.  
4. **Finance team** – cost management access only.  
5. **Analysts** – read-only access to data.  

---

## Key Notes
- The diagram provides only a **baseline**; security improvements must be layered on top.  
- Future adjustments must address:  
  - IAM policies and role separation.  
  - IAM configuration enforcement.  
  - Access policy structures.  
- These steps establish a **strong baseline**, providing real-world alignment with audit and compliance needs.  
