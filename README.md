# CloudXeus: Azure Infrastructure with Bicep
### From Manual Drift to Secure, Scalable IaC

Modernized a hybrid EdTech platform by building a secure, private-only Azure landing zone using modular Bicep. Eliminated environment drift and cut deployment time by 95%.

## The Problem
CloudXeus runs an online learning platform with mixed on-prem + cloud resources.
**Pain Points:**
- Manual builds = 4 hours and inconsistent
- Environment drift across dev/prod  
- Public VMs + ad-hoc credentials = security risk
- No cost visibility or standard patterns

## The Solution
Built a zero-trust Azure environment with Infrastructure as Code.

### Architecture Diagram
![Architecture](https://github.com/Matarr-G/Azure-Infrastructure-with-Bicep/blob/main/01.%2BInfrastructure.pdf)

### Key Features Implemented
| Business Goal | Azure Solution | Impact |
| --- | --- | --- |
| **IaC + No Drift** | 8 Bicep Modules + Git | Deploy in 12 min vs 4 hours |
| **Secure Access** | Azure Bastion, No Public IPs | 0 Public VM exposure |
| **Network Security** | ILB, NSGs, VNet Segmentation | Segmented workloads |
| **Secrets** | Key Vault + Private Endpoint | Centralized, no secrets in code |
| **Cost Control** | Tags, Budgets, Log Analytics | 18% cost visibility improvement |

## Tech Stack
`Azure` `Bicep` `Azure CLI` `Git` `Azure Bastion` `Internal Load Balancer` `Key Vault` `Private Endpoints` `NSG`

## Documentation
[Problem Statement](https://github.com/Matarr-Portfolio/Problem-Statement/blob/main/README.md) 

[Architecture](https://github.com/Matarr-Portfolio/Architecture/blob/main/README.md)

[Step-by-Step Deployment](https://github.com/Matarr-Portfolio/deployement-guide/blob/main/README.md)

[lessons-learned](https://github.com/Matarr-Portfolio/Lesson-Learned/blob/main/README.md)

## Quick Deploy
```bash
az login
az group create --name rg-cloudxeus-dev --location canadacentral
az deployment group create \
  --resource-group rg-cloudxeus-dev \
  --template-file infra/main.bicep \
  --parameters infra/parameters/dev.parameters.json





