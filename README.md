# Azure
# 1. Core Azure Architectural Components
  Azure architecture is built to provide high availability, scalability, security, and global reach.

# 1.1 Regions, Availability Zones, Resource Groups
🔹 Regions
A region is a geographical area containing one or more data centers.

Examples: East US, West Europe, Central India

# Why Regions matter:

Data residency

Disaster recovery

Compliance
# 🔹 Availability Zones (AZ)
Physically separate data centers within a region
Each zone has independent power, cooling, and networking
# Benefits:

High availability

Fault tolerance
# Example:

Deploy VMs across Zone 1, Zone 2, Zone 3

# 🔹 Resource Groups
A logical container for Azure resources

Resources share lifecycle (create, update, delete together)

# Example:

Resource Group: prod-rg
 ├── VM
 ├── Storage Account
 ├── Virtual Network

#  1.2 Azure Resource Manager (ARM)

ARM is the deployment and management layer for Azure.

# Features:
Infrastructure as Code (IaC)

# Consistent management via:

Azure Portal

Azure CLI

PowerShell

ARM templates (JSON/Bicep)

# Example ARM concepts:

Declarative templates

Role-Based Access Control (RBAC)

Tags for cost management

# 1.3 Azure Compute Options

Azure provides multiple compute choices based on control, scalability, and use-case requirements.

| **Compute Service**              | **Description**                                                    | **Example Use Case**                     |
| -------------------------------- | ------------------------------------------------------------------ | ---------------------------------------- |
| **Virtual Machines (IaaS)**      | Full control over operating system and environment                 | Hosting legacy systems                   |
| **App Service (PaaS)**           | Platform-managed environment for building and hosting applications | Deploying .NET, Python, or Java web apps |
| **Containers (AKS / Docker)**    | Lightweight, portable environments for running applications        | Microservices-based applications         |
| **Azure Functions (Serverless)** | Event-driven compute where code runs only when triggered           | Running automated email notifications    |

Example:

If you want a simple solution to run API logic occasionally (like sending OTP), Azure Functions is a cost-effective option because you pay only when the function executes.

# 2. Cloud Concepts

2.1 Cloud Service Models (IaaS, PaaS, SaaS)

IaaS (Infrastructure as a Service)

Provides compute, storage, and networking resources. The user manages OS and applications.

Example:

Running a web server on an Azure Virtual Machine with full configuration control.

PaaS (Platform as a Service)

Azure manages infrastructure and runtime. You only manage your application code and data.

Example:

Deploying a web application using Azure App Service without managing OS, runtime versions, or updates.

SaaS (Software as a Service)

Fully managed software delivered through the cloud.

Example:
Using Microsoft 365 for emails or productivity apps without installing or maintaining any software.

# 2.2 Deployment Models (Public, Private, Hybrid Cloud)
Public Cloud

Services are shared across multiple organizations while remaining secure and isolated.

Example:

Using Azure or AWS to host web apps or storage.

Private Cloud

Resources are dedicated to a single organization, offering higher control and compliance.

Example:

Banks or government agencies operating sensitive applications on a dedicated private cloud setup.

Hybrid Cloud

Combines on-premises infrastructure with public cloud services.

Example:

A company keeps financial databases on-premises (private) while hosting customer-facing applications on Azure (public).

# 2.3 CapEx vs OpEx

CapEx (Capital Expenditure)

Large upfront investment for physical equipment like servers, cooling, and networking.

Example:

Buying physical servers and setting up a data center costing several lakhs.

OpEx (Operational Expenditure)

Pay-as-you-go model where billing is based on resource usage.

Example:
Paying monthly for Azure services based on consumption instead of buying physical hardware.

| **Concept**                      | **Description**                                                        | **Example**                     |
| -------------------------------- | ---------------------------------------------------------------------- | ------------------------------- |
| **Region**                       | Geographic location where Azure services are hosted                    | Central India                   |
| **Availability Zone**            | Physically separate data centers within a region for high availability | Zone 1, Zone 2                  |
| **Resource Group**               | Logical container that holds related Azure resources                   | Resources for an e-commerce app |
| **ARM (Azure Resource Manager)** | Service used to deploy and manage Azure resources                      | ARM Templates                   |
| **IaaS**                         | You manage OS, runtime, and infrastructure                             | Azure Virtual Machine           |
| **PaaS**                         | You manage application and data only                                   | Azure App Service               |
| **SaaS**                         | Fully managed, ready-to-use software                                   | Microsoft 365                   |
| **Public Cloud**                 | Shared cloud infrastructure available to many users                    | Azure Cloud                     |
| **Private Cloud**                | Dedicated cloud infrastructure for one organization                    | Banking systems                 |
| **Hybrid Cloud**                 | Combination of on-premises and public cloud                            | On-prem + Azure                 |
| **CapEx**                        | Capital expenditure with upfront investment                            | Buying physical servers         |
| **OpEx**                         | Operational expenditure with pay-as-you-go model                       | Azure usage-based billing       |

Azure Compute Services

Azure Compute Services provide the processing power required to run applications, scripts, websites, and workloads in the cloud.



