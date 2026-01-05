#AWS-SAA
Theory: https://gemini.google.com/share/015f97f85c55
Architect: QUIZ_LINK

---

**Question 1** The article states that EKS Anywhere allows you to run Kubernetes on your own infrastructure (bare metal, VMs) while still benefiting from a "managed control plane."

In a standard cloud-based EKS environment, AWS is fully responsible for the availability and scalability of the control plane (the master nodes). **Critically analyze how this "Shared Responsibility Model" shifts when you deploy EKS Anywhere on-premises.**

Specifically, if the physical server hosting your EKS Anywhere control plane fails, whose responsibility is it to restore service availability—yours or AWS's—and why does this distinction matter for a business expecting a "cloud-like" experience?

---

**Question 2** The text highlights "Dashboard Integration" as a key benefit, allowing you to see your on-prem clusters (EKS/ECS Anywhere) alongside your cloud clusters in the AWS Console.

Consider a scenario where your on-premises data center loses internet connectivity (the connection to the AWS Region is severed).

**What happens to your EKS/ECS Anywhere cluster during this disconnection?** Does your application stop running? Can you still deploy new containers? Explain what functionality breaks and what survives when that "tether" to AWS is cut.

---

**Question 3** The text distinguishes the two services:

- **ECS Anywhere:** Uses the "ECS Agent" to register instances.
    
- **EKS Anywhere:** Delivers a "consistent Kubernetes experience" using a specific distribution.
    

Imagine you are the Chief Architect for a medium-sized logistics company. You have a few dozen bare metal servers in a warehouse with **unreliable** internet. Your team has strong developers but **very limited DevOps/SRE resources** (no one really knows how to manage `etcd` or debug complex cluster networking).

**Which solution—ECS Anywhere or EKS Anywhere—is the deeper architectural fit for your team, and why?**