# 📦 Lab 07 – Manage Azure Storage

## 📚 Table of Contents
- [Overview](#-overview)  
- [Objectives](#-objectives)  
- [Key Concepts Reinforced](#-key-concepts-reinforced)  
- [Lab Environment & Tools](#-lab-environment--tools)  
- [Tasks Performed](#-tasks-performed)  
- [Outcome Summary](#-outcome-summary)  
- [Business Relevance](#-business-relevance)  
- [Screenshots](#-screenshots)  
- [Acknowledgments](#-acknowledgments)  

---

## 📌 Overview
In this lab, I explored Microsoft Azure Storage services by creating and configuring a storage account, blob containers, and file shares. I secured blob storage using access tiers, immutability policies, and Shared Access Signatures (SAS). I also tested Azure File storage and enforced network restrictions with virtual networks. These steps replicate real-world scenarios for securely managing enterprise storage solutions.

---

## 🎯 Objectives
- Create and configure a geo-redundant storage account.  
- Secure blob containers with immutability and SAS policies.  
- Upload and manage data in Azure blob storage.  
- Create Azure File shares and test file uploads.  
- Restrict access using virtual networks and storage account firewall rules.  

---

## 🧠 Key Concepts Reinforced

| Concept                | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| Azure Storage Account   | Container for blobs, files, queues, and tables with unique namespace access. |
| Blob Storage            | Stores unstructured data (Binary Large Objects), like images or logs.       |
| Immutable Storage       | Write once, read many (WORM) storage, secured with time-based policies.     |
| SAS (Shared Access Signature) | Grants limited, controlled access to blob data.                     |
| Azure File Storage      | Fully managed file shares accessible via SMB and Storage Browser.          |
| Network Restrictions    | Enforcing access limits using virtual networks and service endpoints.       |

---

## 🧰 Lab Environment & Tools
- **Azure Portal** – [https://portal.azure.com](https://portal.azure.com)  
- Resource Group: `az104-rg7`  
- Services Used: Azure Storage Account, Blob Containers, File Shares, Virtual Network, Storage Browser  

---

## 🔧 Tasks Performed
1. **Created and configured a storage account** with Standard performance, Geo-Redundant Storage (GRS), and restricted public access.  
2. **Configured networking** by disabling public access, then later enabling selected networks and adding client IP for testing.  
3. **Set up lifecycle management rule** (`Movetocool`) to automatically move blobs older than 30 days to cool storage.  
4. **Created a private blob container** (`data`) and added a **time-based immutability policy** (180 days).  
5. **Uploaded a blob file** into the container with Hot access tier and confirmed restricted public access.  
6. **Generated a SAS URL** to allow limited, temporary read-only access to the uploaded blob.  
7. **Created an Azure File share** (`share1`) and uploaded a file through Storage Browser.  
8. **Restricted network access** by associating the storage account with a virtual network and removing public IP access.  
9. Validated that storage resources were only accessible from within the configured virtual network.  

---

## 📈 Outcome Summary
By the end of this lab, I successfully provisioned and secured Azure storage resources. I implemented data lifecycle policies, immutable storage retention, SAS-based controlled access, and tested Azure File shares. Restricting access at the network level demonstrated enterprise-grade security practices.

---

## 🏢 Business Relevance
Enterprises rely on Azure Storage to reduce costs, enforce compliance, and secure business-critical data. This lab mirrors real-world scenarios where organizations must:  
- Enforce compliance with **immutability policies** (e.g., HIPAA, FINRA, GDPR).  
- Use **cool storage tiers** to reduce cost for infrequently accessed data.  
- Secure access to storage accounts with **SAS tokens** and **virtual networks**.  
- Leverage **Azure File shares** to migrate or replace on-premises file servers.  

---

## 📸 Screenshots  

| Task | Screenshot | Caption |
|------|------------|---------|
| Task 1 – Review + Create | ![Storage account creation](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20ex%201%20t%201(1).png?raw=true) | Final **Review + Create** page before deploying the storage account with Standard performance and RA-GRS redundancy. |
| Task 1 – Storage Account Overview | ![Storage account overview](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20ex%201%20t%201(2).png?raw=true) | Overview blade showing deployed storage account properties including replication and security settings. |
| Task 1 – Lifecycle Rule | ![Lifecycle rule](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20ex%201%20t%201(3).png.png?raw=true) | `Movetocool` lifecycle management rule configured to move older blobs to cool storage. |
| Task 2 – Immutable Policy | ![Immutable policy](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%202(1).png?raw=true) | Blob container `data` configured with **time-based immutability retention** of 180 days. |
| Task 2 – Container View | ![Container view](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%202(2).png.png?raw=true) | Viewing `data` container contents including uploaded `securitytest` folder. |
| Task 2 – Blocked Public Access | ![Blocked access](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%202(3).png.png?raw=true) | Direct blob access denied with **PublicAccessNotPermitted** message since the container is private. |
| Task 2 – Generate SAS (Setup) | ![Generate SAS setup](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%202(4).png?raw=true) | SAS token setup dialog opened to generate temporary read-only access to blob. |
| Task 2 – Generate SAS (Expiry) | ![Generate SAS expiry](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%202(5).png?raw=true) | SAS configuration specifying **start and expiry date/time** for limited access. |
| Task 3 – Create File Share | ![Create file share](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%203(1).png?raw=true) | Creating Azure File Share `share1` with transaction-optimized tier. |
| Task 3 – Storage Browser | ![Storage browser](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%203(2).png?raw=true) | `share1` file share visible in **Storage Browser** under file shares. |
| Task 3 – File Share Overview | ![File share overview](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%203(3).png?raw=true) | `share1` file share properties showing redundancy and configuration settings. |
| Task 3 – Virtual Network Creation | ![Virtual network](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%203(4).png?raw=true) | Creating new virtual network `vnet1` in East US region. |
| Task 3 – Add Service Endpoint | ![Service endpoint](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%203(5).png?raw=true) | Adding **Microsoft.Storage** service endpoint to the `vnet1/default` subnet. |
| Task 3 – Restrict Networking | ![Restrict networking](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%203(6).png?raw=true) | Restricting storage account access to only the `vnet1/default` subnet. |
| Task 3 – Access Blocked by Firewall | ![Access blocked](https://github.com/miadco/az104-labs/blob/main/lab07-configure-monitoring/screenshots/lab%207%20t%203(7).png?raw=true) | Attempt to access file share blocked with **not authorized** error after VNet-only restriction applied. |

---

## 🙏 Acknowledgments
Lab instructions sourced from the official [AZ-104 Microsoft Learning Labs – Lab 07](https://microsoftlearning.github.io/AZ-104-MicrosoftAzureAdministrator/Instructions/Labs/LAB_07-Manage_Azure_Storage.html).  
AI assistance was used to structure documentation and captions.
