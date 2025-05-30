**VPC Peering** enables **private, point-to-point network connectivity** between two [VPC](VPC.md)s, allowing instances to communicate **as if they were in the same network**.

![Pasted image 20250529210342.png](_atts/Pasted%20image%2020250529210342.png)
#### 🔹 **Key Features:**

- Connects **VPCs within the same AWS account**, **across accounts**, or even **across regions** (inter-region peering).
    
- **No gateway, VPN, or separate physical hardware** required.
    
- Traffic stays on the **AWS global backbone**—**low latency**, **high bandwidth**, and **secure**.
    

#### 🔹 **Limitations:**

- **No transitive routing** – VPC A peered with B, and B peered with C **does not allow A ↔ C** communication.
    
- **CIDR blocks must not overlap.**
    
- **Manually update route tables** in each VPC to enable traffic flow.
    
- **No DNS resolution by default** between VPCs unless **"enable DNS resolution"** is checked.
    

#### 🔹 **Use Cases:**

- Microservices architecture with isolated VPCs
    
- Shared services VPC (e.g., central logging or authentication)
    
- Multi-account environments using AWS Organizations
    

#### 🔹 **Setup Steps:**

1. Create a **peering connection** (from requester VPC to accepter VPC).
    
2. Accept the connection in the **target VPC**.
    
3. Update **route tables** in both VPCs.
    
4. (Optional) Enable **DNS resolution** if needed.
    

---

Let me know if you want to add **Transit Gateway** as a comparison or a diagram to visualize peering!