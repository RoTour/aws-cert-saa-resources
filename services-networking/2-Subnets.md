Theory: https://gemini.google.com/share/5ddef4464827
Architect: https://gemini.google.com/share/eecf80397601

---

**Question 1: The "Small Subnet" Trap**

The text states that AWS reserves **5 IP addresses** in every single subnet (Network, Router, DNS, Future, Broadcast). It also states the smallest allowed subnet is a `/28`.

Let's do the math. A `/28` CIDR block provides **16 total IP addresses** ($2^{(32-28)} = 16$).

If you design a subnet with a /28 mask, how many actual EC2 instances can you launch in it?

Furthermore, why is choosing a /28 almost always a bad idea for services that scale automatically, like a Kubernetes cluster or a fleet of Load Balancers?

---

**Question 2: Architecture & Availability Zones**

The text emphasizes: _"Every subnet is associated with a single availability zone."_

**Scenario:** You are architecting a standard 3-tier web application (Web Tier, App Tier, Database Tier).
- You need **High Availability** (tolerance if one data center fails).
- You decide to use **2 Availability Zones** (e.g., us-east-1a and us-east-1b).    

**Part A:** What is the **minimum number of subnets** you must create to host this 3-tier application across 2 zones, keeping the layers (Web, App, DB) properly segmented?

**Part B:** If a hurricane hits the data center for `us-east-1a` and destroys it, can you simply "migrate" the subnets from Zone A to Zone B to restore service? Why or why not?

