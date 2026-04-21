# Thought Process

---

## Why is the DataSubnet NSG configured to deny all internet traffic?
What types of resources would go in this subnet and why shouldn't they be internet-accessible?

**Answer:**  
The DataSubnet NSG is configured to deny all internet traffic to protect sensitive backend resources such as databases and internal services.  

These types of resources handle critical data and do not require direct public access. Allowing internet exposure would increase the risk of unauthorized access, attacks, or data breaches. Keeping them private ensures better security and controlled access through internal networks only.

---

## What would happen if the Storage Account allowed public blob access instead of private?
Describe a real-world scenario where this could cause a data breach.

**Answer:**  
If public blob access is enabled, anyone with the URL can access the stored files without authentication.  

In a real-world scenario, this could expose sensitive data such as customer records or financial information. For example, if a bank stores user information or transaction data in a publicly accessible storage account, attackers could retrieve and misuse that data, leading to data breaches, legal consequences, and loss of trust.

---

## What is your Azure Advisor score?
What specific improvements does it suggest? Would you implement all of them — why or why not?

**Answer:**  
My Azure Advisor score is **75%**.  

It suggests improvements in areas such as:
- Security  
- Networking  
- Virtual machine protection  

I would prioritize implementing the security-related recommendations first because they directly reduce risk. Not all recommendations may be immediately necessary, especially if they increase cost or are not critical to the current environment, so they should be evaluated based on impact and priority.

---

## Your VM currently has a public IP and SSH (port 22) open.
In a production environment, what would you do differently?

**Answer:**  
In a production environment, I would avoid exposing SSH directly to the internet.  

Instead, I would:
- Use a private IP with VPN or Azure Bastion for secure access  
- Restrict access using Network Security Groups (NSGs)  
- Enable Just-In-Time (JIT) access to limit exposure time  
- Use SSH key-based authentication instead of passwords  

This reduces the attack surface and improves overall security.

---

## You chose LRS for the Storage Account.
A manager asks: "What happens if the entire datacenter goes down?" How do you respond?

**Answer:**  
LRS stores data within a single datacenter, so if that datacenter goes down, the data may become unavailable or even lost.  

To address this, I would recommend using Geo-Redundant Storage (GRS), which replicates data to another region. This ensures higher availability and resilience in case of a full datacenter failure.
