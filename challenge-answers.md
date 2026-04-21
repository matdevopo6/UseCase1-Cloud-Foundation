# Challenge Answers

---

## Scenario 1
**Scenario:**  
NovaTech's CTO asks you to ensure the web server is accessible from the internet but the database server (in DataSubnet) should never be directly reachable. A new developer accidentally creates a VM in DataSubnet with a public IP. What Azure feature would prevent this from happening again?

**Answer:**  
I will make use of Azure Policy.  
It can enforce rules like “deny public IP creation in specific subnets” and prevent non-compliant resources from being deployed, even if NSGs are misconfigured.

---

## Scenario 2
**Scenario:**  
The CFO is concerned about the cost of running all infrastructure in a single region. They ask: "What happens to our web server if the East US region goes completely offline?" How would you design for this? What Azure services would you recommend?

**Answer:**  
Design a multi-region architecture:
- Use Azure Traffic Manager or Front Door for failover  
- Deploy web servers in at least two regions  
- Use geo-redundant storage (GRS) for data replication  

This ensures the application stays available even if one region fails.

---

## Scenario 3
**Scenario:**  
An auditor asks you: "How do you know who created or modified resources in your Azure environment?" Which Azure service provides this audit trail, and where would you find it?

**Answer:**  
I will make use of Azure Activity Log.  
It records all create, modify, and delete actions. You can view it in the Azure Monitor → Activity Log section.

---

## Scenario 4
**Scenario:**  
NovaTech's storage account currently uses LRS. The company handles customer financial data. The compliance team requires data to survive a complete datacenter failure. What would you change, and what are the cost implications?

**Answer:**  
Change from LRS to GRS.  
This ensures data survives a full datacenter failure by duplicating it to another region.

**Cost implication:**  
GRS is more expensive than LRS due to cross-region duplication and higher storage overhead.

---

## Scenario 5
**Scenario:**  
You need to give a contractor temporary access to upload files to the blob container without giving them full Storage Account keys. What Azure feature allows this?

**Answer:**  
Make use of a Shared Access Signature (SAS) token.  
It provides time-limited, permission-controlled access without exposing storage account keys.
