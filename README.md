# Scenario — Current-State AWS Architecture Diagram (StartupCo)

**Objective**  
Create a detailed, current-state AWS architecture diagram that reflects infrastructure and security posture with clear visuals and annotations.

---

## Current Setup (call out explicitly)
- Work is performed from the **AWS root account**.  
- **No role/permission separation** between teams.  
- **MFA** and **password policies** are **not enabled**.  
- **AWS credentials are shared** in team chat.  

**Action:** Summarize what this implies for the organization (risks, gaps, priority fixes).

---

## Current Infrastructure (visual components)
- **EC2** instances running the application (show multiple instances in **Dev** and **Prod**).  
- **S3** buckets for user data and application assets.  
- **RDS** for user information.  
- **CloudWatch** for monitoring and logging.  
- Clearly **separate Dev vs. Prod** environments.

---

## Team Structure & Access Needs (annotate on the diagram)
- **4 Developers:** EC2 and S3 access.  
- **2 Operations:** Full infrastructure access.  
- **1 Finance Manager:** Billing and cost-management access.  
- **3 Data Analysts:** Read-only access to data resources.

---

## Diagram Guidance
- Use standard AWS icons; label **data flows** (dotted lines) and **dependencies** (arrows).  
- Include **trust boundaries**, clear labels, and a **legend** for team access roles.  
- Place annotations directly on the diagram and keep **Dev** and **Prod** visually separated.
