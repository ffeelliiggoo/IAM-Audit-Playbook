# Scenario — Current-State IAM Deployment (StartupCo)

## Client Background
You are engaged as a Cloud Engineer Consultant for **StartupCo**, a fast-growing tech startup that recently launched its first product — a fitness tracking application.  

StartupCo has been using AWS for three months. To meet aggressive launch deadlines, the team set up infrastructure quickly without implementing security best practices.  

Currently:  
- The company has **10 employees**, all using the **AWS root account credentials** to access and manage resources.  
- Credentials are shared in team chat.  
- No MFA, password policies, or role separation have been enforced.  

The **CTO** now recognizes the security risks of this setup and has asked for a remediation plan to establish proper IAM governance.

---

## Objective
Create a **detailed, current-state AWS architecture diagram** that reflects the infrastructure and security posture, with annotations highlighting risks, gaps, and recommendations.

---

## Current Setup (to highlight explicitly)
- All work is performed using the **AWS root account**.  
- **No separation of permissions** between teams.  
- **No MFA** or enforced password policies.  
- **Root credentials** are openly shared.  

**Action:** Summarize risks, gaps, and priority fixes resulting from this setup.

---

## Current Infrastructure (visual components)
- **EC2** instances running the application (multiple instances in **Dev** and **Prod**).  
- **S3** buckets for user data and application assets.  
- **RDS** database for user information.  
- **CloudWatch** for monitoring and logging.  
- **Development and Production** environments not clearly separated.

---

## Team Structure & Access Needs (annotate on the diagram)
- **4 Developers:** EC2 + S3 access.  
- **2 Operations:** Full infrastructure access.  
- **1 Finance Manager:** Billing and cost-management tools.  
- **3 Data Analysts:** Read-only access to data resources.

---

## Remediation Tasks

### 1. Create Architecture Baseline
- Document and diagram the current-state infrastructure.  
- Highlight insecure practices (root usage, shared credentials, no MFA).  

### 2. Secure the Root Account
- Enable MFA.  
- Stop using the root account for daily operations.  
- Store root credentials securely (vault/secret manager).  

### 3. Create IAM Users and Groups
- **Developer group:** Application EC2, S3, and CloudWatch log viewing.  
- **Operations group:** Full EC2, RDS, CloudWatch, and Systems Manager access.  
- **Finance group:** Billing tools (Cost Explorer, AWS Budgets), read-only access.  
- **Analyst group:** Read-only S3 and database access.  

### 4. Enforce Security Requirements
- Require MFA for all users.  
- Implement a strong password policy.  
- Ensure least-privilege access — users only access what they need.  

---

## Areas to Cover

- **IAM Governance**: Account hierarchy, root protections, and role separation.  
- **Access Management**: Users, groups, roles, and least-privilege enforcement.  
- **Credential Security**: MFA, password policies, key management, and secret handling.  
- **Monitoring & Detection**: IAM activity monitoring, CloudTrail integration, anomaly detection.  
- **Audit & Review**: Access recertification process, control documentation, and risk register updates.  
- **Integration Security**: API and third-party access validation, federation patterns, SaaS alignment.  
- **Technical Debt Identification**: Document shortcuts (e.g., shared credentials, manual syncs) and align fixes to risk reduction.  

---

## Advanced Bonus Challenge
Recreate the IAM solution using **Infrastructure as Code**:  
- Terraform  
- AWS CloudFormation  
- AWS CDK  

This helps establish reproducibility, reduce technical debt, and improve strategic planning.

---

## Key Note
This is a **pilot/POC exercise**. Actual AWS resources are not being provisioned; the goal is to **design and document** a secure IAM setup to replace poor practices and lay a foundation for future governance.
