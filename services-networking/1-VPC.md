Theory: https://gemini.google.com/share/9be666c1c8a7
Architect: https://gemini.google.com/share/034f17ec83eb

---

**Question 1: Regional Isolation**

The text explicitly states that a VPC "exists solely within its designated region" and prevents cross-region communication by default.

From a Solutions Architect's perspective, why is this strict regional isolation beneficial for your infrastructure? Conversely, if you are designing a global application serving users in the US, Europe, and Asia, what specific design challenge does this isolation create for you?

---

**Question 2: CIDR Block Strategy**

The text states that a VPC CIDR block can range from a /16 (65,536 addresses) to a /28 (16 addresses).

Imagine you are designing an architecture for a company with many different departments (HR, Finance, Dev, Prod), and each needs its own VPC.

Why wouldn't you just assign the largest possible block (/16) to every single VPC to ensure you never run out of IP addresses? What implies the "risk" or architectural headache of being wasteful with IP ranges?

---

**Question 3: Security Layers**

The text mentions two security features: **Security Groups (SGs)** and **Network Access Control Lists (NACLs)**.

The text notes that the Default Security Group allows outbound traffic but blocks inbound by default (until you add rules), while the Default NACL allows _everything_.

**Scenario:** You have a web server in a subnet.
1. You configure the **Security Group** to allow inbound HTTP traffic (port 80).
2. You accidentally configure the **NACL** to DENY inbound HTTP traffic (port 80).

**Will a user on the internet be able to reach your web server? Why or why not?** (Think about the order in which these checks happen).

---

**Question 4: Default vs. Custom VPC**

The text mentions that the Default VPC comes with:

Subnets in every Availability Zone.

An Internet Gateway (IGW) attached.

A route table that sends traffic 0.0.0.0/0 (all traffic) to that Internet Gateway.

This setup is great for launching a web server quickly. However, imagine you are launching a highly sensitive database containing customer credit card numbers.

Why is deploying this database into a subnet in the Default VPC a potential security risk, specifically regarding its network exposure? (Focus on what defines a "Public" vs. "Private" subnet).

---

