# IAM-Audit-Playbook

## Purpose
Provide a structured process to evaluate identity and access management (IAM) practices, uncover security control gaps, and identify technical debt that affects organizational security posture.

---

## 1. Current State Assessment

**Objective:** Document how IAM is being used today.

- Identify account structures, authentication methods, and credential management.  
- Review existing permissions, roles, and group assignments.  
- Determine if shared accounts, root account usage, or weak configurations (e.g., no MFA) are present.  
- Note any missing password or key rotation policies.  

---

## 2. Security Risks and Technical Debt

- **Security Risks:** Loss, disruption, or compromise of systems/data due to vulnerabilities, misconfigurations, or weak controls.  
- **Technical Debt:** Incomplete or suboptimal IAM decisions made under time or resource pressure that must be addressed later.  

**Intersection Points:**  
1. Technical debt introduces risk exposure (e.g., undocumented accounts, shared credentials).  
2. Deferred security controls become debt (e.g., postponing MFA or logging).  
3. Shortcuts in IAM integration create hidden gaps (e.g., no federation review, manual role syncs).  
4. Unresolved debt becomes harder to assess and remediate without documentation.  

---

## 3. Audit Review Components

### Access Controls
- Root account usage and protections (MFA, monitoring).  
- Separation of duties across teams and environments.  
- Role-based access control (RBAC) enforcement.  
- Third-party integrations and API access governance.  

### Credential Management
- Password complexity and rotation policies.  
- API key usage and expiration.  
- Key management practices (KMS, secret managers).  

### Monitoring and Logging
- IAM activity monitoring (CloudTrail, SIEM integration).  
- Detection of anomalous or privileged access events.  
- Retention of IAM-related logs for audit and compliance.  

### Documentation and Governance
- Access review frequency and recertification process.  
- Documentation of architecture, controls, and integration patterns.  
- Risk register entries for unresolved IAM issues.  

---

## 4. Best Practices for Remediation
- Require documentation of IAM architecture and access flows.  
- Track IAM-related technical debt in a backlog or risk register.  
- Address access risks during onboarding, not after deployment.  
- Treat partial mitigations (e.g., manual access reviews, incomplete MFA rollout) as risks.  
- Align with vendor IAM best practices but define governance standards internally.  

---

## 5. Deliverables
- **IAM Architecture Diagram:** Show current access model, flows, and trust boundaries.  
- **Control Mapping Table:** IAM domains vs. compliance frameworks (CIS, NIST, PCI).  
- **Gap Register:** Identified risks, technical debt, remediation recommendations, and ownership.  
- **Summary Report:** Key findings, business impact, and prioritized actions.  

---

## 6. Real-World Consideration
Organizations often start with quick, ad-hoc IAM setups and later transition to structured governance. Identifying and addressing IAM-related technical debt early reduces long-term exposure and builds resilience.
