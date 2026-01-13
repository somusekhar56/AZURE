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
# 3. Azure Compute Services Overview

Azure offers different compute options depending on the level of control, scalability, and purpose.

Azure Compute Service provides on-demand computing resources to run applications, workloads, and services in the cloud.

# 3.1 Virtual Machines (VMs)

Azure Virtual Machines allow you to run Windows or Linux systems in the cloud, similar to a physical computer.
# 3.1.1 VM Sizing, Pricing, and Scaling

VM Sizing: VMs are available in different configurations based on CPU, RAM, and disk type.
| **VM Type**           | **Example** | **Best For**                          |
| --------------------- | ----------- | ------------------------------------- |
| **General Purpose**   | B2s, D2s    | Development environments, Web servers |
| **Compute Optimized** | F-series    | High CPU-intensive workloads          |
| **Memory Optimized**  | E-series    | Databases, in-memory applications     |
| **GPU VMs**           | NV-series   | AI / ML, graphics-intensive workloads |
| **High Performance**  | H-series    | Scientific computing, simulations     |
# Pricing Model:

Pay-As-You-Go: Pay only when running.
Reserved Instances: Cheaper if committed for 1–3 years.

# Scaling:
Scale VM size up or down based on demand.
3 Example: During festive sales, increase size from D2s → D8s.

# 3.1.2 VM Deployment and Management
VMs can be deployed using:

Azure Portal

Azure CLI(Command-Line Interface)

PowerShell

ARM Templates(Azure Resource Manager Templates)

Terraform

You can manage them using SSH (Linux) or RDP (Windows).

SSH is a secure protocol used to remotely access and manage Linux servers over an encrypted connection.Client sends connection request Server verifies key/password

In Azure, RDP(Remote Desktop Protocol) is used to remotely access and manage Windows Virtual Machines through a graphical interface.Create a Windows VM,Azure assigns a Public IP
Open port 3389 in NSG (Network Security Group)
# Example Use Case:
A payroll server is deployed as a Windows VM and maintained manually.
# 3.2 Azure App Services
Azure App Service is a Platform-as-a-Service (PaaS) for hosting web applications, REST APIs, and mobile backends without managing underlying infrastructure.

# Azure automatically handles:
OS patching

Load balancing

Auto-scaling

CI/CD support

Deployment slots

# Example Use Case:
Deploy a Python Flask API or Node.js web app without worrying about OS.
# 3.3 Azure Functions (Serverless)
Azure Functions allow you to run event-driven code without provisioning servers.

You only pay for execution time (milliseconds).
# Triggers examples:
| **Trigger Type**  | **Example**                           |
| ----------------- | ------------------------------------- |
| **Blob Trigger**  | Resize an image when it is uploaded   |
| **Timer Trigger** | Run daily automated cleanup jobs      |
| **HTTP Trigger**  | Works like an API endpoint            |
| **Queue Trigger** | Process asynchronous background tasks |
# Example Use Case:
When a user uploads an image, a function compresses and stores it.
# 3.4 Azure Kubernetes Service (AKS)
Azure Kubernetes Service is used for managing containerized applications using Docker + Kubernetes.
# It provides:
Auto scaling

Load balancing

Self-healing containers

Blue-green deployments
# Example Use Case:
A banking microservices system (login, payment, alerts) deployed as containers and managed through AKS.
# 3.5 Cloud Service Models
Azure offers multiple cloud consumption models.
| **Model** | **Responsibility**             | **Example Services**   | **Analogy**                               |
| --------- | ------------------------------ | ---------------------- | ----------------------------------------- |
| **IaaS**  | You manage OS and applications | Azure VM               | Renting an empty house and customizing it |
| **PaaS**  | Only deploy and manage code    | App Service, Azure SQL | Furnished apartment                       |
| **SaaS**  | Everything is managed          | Office 365, Gmail      | Hotel stay                                |

# When to Use What?
| **Requirement**                                | **Best Option**                |
| ---------------------------------------------- | ------------------------------ |
| Full control over OS and applications          | Virtual Machines               |
| Host a website or API with minimal management  | App Service                    |
| Event-driven automation or short-running tasks | Azure Functions                |
| Microservices or container orchestration       | AKS (Azure Kubernetes Service) |
| Fully ready-to-use software                    | SaaS model                     |
# Summary
VMs → Maximum control, manual management.

App Services → Deploy apps without managing servers.

Azure Functions → Serverless, event-driven automation.

AKS → Container orchestration for microservices.

Cloud Models → Decide level of ownership (IaaS, PaaS, SaaS).

# 4. Azure Storage Services
Azure Storage Services allow applications to securely store and retrieve data with massive scalability, durability, and cost flexibility.
# 4.1 Blob Storage
Azure Blob Storage is Microsoft's object storage designed to handle unstructured data such as logs, images, videos, backups, and datasets.
#  Key Concepts
# Component	        Description
Storage Account 	Container for all storage services
Container	        Logical group of blobs (like folder)
Blob	            The actual stored data file
# Blob Types
# Blob Type	    Use Case
Block Blob	    Text, binary, backups, images
Append Blob	    Log files (append-only)
Page Blob	      Virtual Machine disks

# Real Example:
If you upload profile pictures in a mobile app, they are stored in Blob Storage.
# Example Command (Upload Blob)
az storage blob upload \
  --account-name mystorage123 \
  --container-name uploads \
  --name image1.png \
  --file ./image1.png

 3  4.2 Storage Tiers and Replication
Storage tiers help optimize cost based on how frequently data is accessed.
📌 Access Tiers
| **Tier**    | **Best For**                            | **Storage Cost** | **Access Cost** |
| ----------- | --------------------------------------- | ---------------- | --------------- |
| **Hot**     | Frequently accessed data                | High             | Low             |
| **Cool**    | Occasionally accessed data              | Medium           | Medium          |
| **Archive** | Rarely accessed data (logs, compliance) | Lowest           | Highest         |

📌 Replication Strategies
| **Replication Type**                | **Durability Level** | **Description**                               |
| ----------------------------------- | -------------------- | --------------------------------------------- |
| **LRS** (Locally Redundant Storage) | Local                | Data replicated within a single datacenter    |
| **ZRS** (Zone-Redundant Storage)    | Zone level           | Replicated across multiple availability zones |
| **GRS** (Geo-Redundant Storage)     | Cross-region         | Data replicated to a secondary region         |
| **RA-GRS** (Read-Access GRS)        | Cross-region + Read  | Read access available from secondary region   |

# Real Example:
A banking application stores audit logs using Archive tier + GRS for compliance and disaster recovery.

# 4.3 Access Control & Shared Access Signatures (SAS)
Azure provides multiple security methods to control who can access data.

# Access Mechanisms
 # Type	          Purpose
Access Keys	    Full admin access (avoid sharing)
RBAC	          Assign permissions using Azure AD roles
SAS Token	      Temporary secure access with expiration
# SAS Example
https://storage.blob.core.windows.net/files/data.csv?sp=r&st=2025-12-01&se=2025-12-02&sig=XA12BCXD==
This URL gives read-only access until the expiration time.

# 5. Azure Key Vault, Azure Functions, and Azure Logic Apps
# 5.1 Azure Key Vault
Azure Key Vault securely stores:

Secrets (passwords, API keys)

Keys (cryptographic encryption)

Certificates (SSL/TLS)
# 🧠 Real Example:

Instead of storing DB password in code, your application retrieves it securely from Key Vault.

# Example Access Code (Python)

from azure.identity import DefaultAzureCredential

from azure.keyvault.secrets import SecretClient

client = SecretClient(vault_url="https://myvault.vault.azure.net/", credential=DefaultAzureCredential())

secret = client.get_secret("db-password")

print(secret.value)

# 5.2 Azure Functions (Serverless)

Azure Functions allow running code only when triggered (event-based).

# 📌 Triggers Supported
HTTP requests

Blob created

Timer schedules

Queue messages
# 🧠 Real Example:
When a file is uploaded into Blob Storage → trigger a function to resize an image or validate file format.

# Example Code (HTTP Trigger)
def main(req):
    return "Function executed successfully!"

3 5.3 Azure Logic Apps
Logic Apps help automate workflows using low-code/no-code visual builder.

📌 Common Use Cases
| Use Case      | Example                                         |
| ------------- | ----------------------------------------------- |
| Notifications | Send an email when a blob is uploaded           |
| Integration   | Connect Salesforce, Microsoft Teams, SharePoint |
| Automation    | Move files between different storage systems    |

🧠 Real Example:
"Send an email to HR when a new employee document is uploaded to Blob Storage."

# 6. Azure Data Services
Azure Data Services support data integration, storage, analytics, and ETL pipelines.

# 6.1 Azure Data Factory (ADF)
Azure Data Factory is an ETL orchestration service to move and transform data across sources.

# 6.1.1 Data Ingestion & Transformation
ADF supports ingestion from:

SQL Server

AWS S3

REST API

On-prem CSV files

Blob Storage
# 🧠 Real Example:
Copy CSV from AWS S3 → clean and transform → load into Azure SQL Database.

# 6.1.2 Pipelines and Activities
| Concept  | Meaning                                                |
| -------- | ------------------------------------------------------ |
| Pipeline | Group of activities that define a complete workflow    |
| Activity | Single ETL step (Copy, Transform, Execute Notebook)    |
| Trigger  | Schedule-based or event-based activation of a pipeline |

# Example Pipeline Steps
Copy CSV from Blob Storage to staging

Run Data Flow to clean data

Load into Azure SQL Database

Send completion report

# 6.2 Azure SQL Database
Azure SQL Database is a fully managed relational database service.

# 📌 Key Features
Automatic scaling

Automated backups

Disaster recovery

Built-in security and auditing
# 🧠 Real Example:
Store application user information and query it using SQL.

# Example SQL Query
CREATE TABLE Users (
  ID INT PRIMARY KEY,
  Name NVARCHAR(100),
  Email NVARCHAR(100)
);

INSERT INTO Users VALUES (1, 'somusekhar', 'somusekhar6384@gmail.com');

SELECT * FROM Users;
# 📌 Summary Table
| Service             | Purpose                                         |
| ------------------- | ----------------------------------------------- |
| Blob Storage        | Store unstructured data (images, videos, files) |
| Storage Replication | Ensure data durability and high availability    |
| SAS & RBAC          | Secure and controlled access to resources       |
| Key Vault           | Secure secrets, keys, and certificates          |
| Azure Functions     | Run serverless, event-driven code               |
| Logic Apps          | Automate workflows and system integrations      |
| Data Factory        | Build and manage ETL/ELT pipelines              |
| Azure SQL           | Fully managed relational structured database    |

# 🚀 Next Recommended Topics
Azure Virtual Networks

Azure Synapse Analytics

Terraform for Infrastructure as Code

CI/CD with Azure DevOps









