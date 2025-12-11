Theory: https://gemini.google.com/share/f67b202a0577
Architect: https://gemini.google.com/share/a1f5dadb085a

---
**Critical Thinking Question 1**

The text highlights a fundamental difference in availability:
- **Internet Gateway (IGW):** "Horizontally scaled... spans all Availability Zones within a region."
- **NAT Gateway:** "Tied to specific Availability Zones... not region-resilient."
    
**Question:** Imagine you have a critical application running on EC2 instances in Private Subnets across **three Availability Zones** (Zone A, Zone B, Zone C).

If you deploy only **one** NAT Gateway in Zone A to save money, and update all three private route tables to point to it, what exactly happens to the instances in Zone B and Zone C if **Zone A goes offline**?

Why does the architecture of the Internet Gateway prevent this same failure scenario from happening to Public Subnets?

---

**Critical Thinking Question 2**

The text explains two ways to handle IP translation:
1. **Public Subnet (IGW):** AWS maps a specific Public IP to the instance's Private IP (1-to-1 mapping).
2. **Private Subnet (NAT GW):** The NAT Gateway manages traffic for many instances using its own single Public IP (Many-to-1 mapping).
    

**Question:** The text states that NAT Gateways "block unsolicited inbound traffic." However, when your private server downloads a patch, the file data coming _back_ from the internet is technically "inbound" traffic.

**How does the NAT Gateway distinguish between a malicious "unsolicited" connection attempt (which it blocks) and the legitimate "return traffic" for your download (which it allows)?**
