Azure $200 Credits & AZ-900 - Professional Notes
*Authored by Humaira Akram | Security Researcher | GHSA CVSS 10.0*

This repository contains my consolidated, hands-on notes from Azure Fundamentals (AZ-900) and practical cost-optimization strategies for the Azure $200 free trial. Documented from a security-first perspective.

Section 1: Azure Free Account - Cost Optimization

*Entitlement:*
- $200 credit valid for 30 days
- 12 months of limited free services + Always free tier

*Cost Control Framework (Production-Grade Practice):*
1.  *Resource Group Isolation:* Create a dedicated RG `rg-sandbox-cleanup` for all lab work. This allows for atomic deletion and prevents orphaned resources.
2.  *Budget Alerts:* Navigate to Cost Management > Budgets. Create a $5.00 budget with 80% and 100% email alerts to avoid unexpected charges.
3.  *Cleanup Policy:* Execute `az group delete --name rg-sandbox-cleanup --yes` after each lab session. Public IPs and Standard SSD Disks are primary cost drivers if left running.
4.  *Recommended Free Tier for AZ-900 Labs:*
        - Compute: B1s Burstable VM (750 hours/month)
        - Storage: LRS Hot Tier, 5GB
        - Database: Azure SQL - 250GB S0

Section 2: AZ-900 - Core Domains

*Domain 1: Cloud Concepts (25-30%)*
- *Economics:* CapEx (Upfront infrastructure) vs OpEx (Pay-as-you-go). Consumption-based model.
- *Deployment Models:* Public, Private, Hybrid. Use case: Financial services often require Hybrid for compliance.
- *Service Models:*
    - IaaS: You manage OS, Middleware, Data. Azure manages Hardware, Network. (e.g., Azure VM)
    - PaaS: You manage Application & Data. Azure manages the rest. (e.g., App Service, Azure SQL)
    - SaaS: Fully managed. You consume the software. (e.g., M365, Dynamics)
- *Core Benefits:* High Availability (SLA 99.9% - 99.99%), Scalability (Vertical & Horizontal), Elasticity, Fault Tolerance, Disaster Recovery.

*Domain 2: Azure Architecture & Services (35-40%)*
- *Global Infrastructure:* Region (Geographic location), Availability Zone (3+ physically isolated datacenters per region), Region Pairs (For DR replication).
- *Management Hierarchy:* Management Group > Subscription > Resource Group > Resource.
- *Compute:* Virtual Machines, Virtual Machine Scale Sets (Autoscaling), App Services (PaaS hosting), Azure Functions (Serverless), Container Instances / AKS.
- *Networking:* Virtual Network (VNet), Subnetting, Network Security Group (NSG - Layer 4 Firewall), Azure Firewall (Layer 7), Load Balancer, Application Gateway, VPN Gateway, ExpressRoute.
- *Storage:* Storage Account, Blob Storage (Object storage - Hot/Cool/Archive tiers), File Storage (SMB), Managed Disks, Redundancy Options: LRS, ZRS, GRS, RA-GRS.
- *Databases:* Azure SQL (PaaS), Cosmos DB (Globally distributed NoSQL), MySQL/PostgreSQL PaaS.

*Domain 3: Management & Governance (30%)*
- *Identity (Entra ID):* Users, Groups, Role-Based Access Control (RBAC) - Owner, Contributor, Reader, Custom Roles. Principle of Least Privilege is critical.
- *Security:* Microsoft Defender for Cloud (CSPM, Secure Score), Microsoft Sentinel (Cloud-native SIEM/SOAR), Azure Key Vault (Secrets, Keys, Certs management), Microsoft Entra - MFA, Conditional Access, SSO.
- *Governance:* Azure Policy (Enforce organizational standards), Resource Locks (CanNotDelete, ReadOnly), Tags (For billing and management), Cost Management.
- *Shared Responsibility Model:* Microsoft is responsible for Physical Host, Network, Datacenter. Customer is responsible for Data, Endpoints, Access Management, and Configuration.

*Study Resources Used:*
- Microsoft Learn - AZ-900 Learning Path (Official)
- John Savill - AZ-900 Study Cram
- Hands-on implementation in $200 sandbox environment.

*Contact:* Twitter / X: @Humaira0924 | Founder: bugbounty-learning-hub

> If this repository helped you, please consider starring it.
