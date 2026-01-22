#AWS-SAA
Theory: https://gemini.google.com/share/8110e6515b99
Architect: https://gemini.google.com/share/75f809cdeb40

---
### Critical Thinking Question 1

Imagine you are planning a migration for a highly secure banking environment. You have hundreds of legacy servers, and it is vital to understand exactly which processes are communicating with each other to map out dependencies accurately before moving anything. However, the security compliance team has a strict policy minimizing the installation of any external software on production servers to reduce the attack surface.

**Analyze the conflict between "Agent-based" and "Agentless" discovery in this specific scenario.**

Which method is technically required to get the process-level visibility you need, and how does that requirement conflict with the security constraint? How would you articulate this trade-off to the security team?

---

### Critical Thinking Question 2

You have run the Discovery phase and collected data for a month. Your on-premises database server has 64GB of RAM and 16 vCPUs.

However, the AWS Migration Hub Assessment report recommends migrating this to an EC2 instance that only has 32GB of RAM and 8 vCPUs.

**Why would the Migration Hub suggest a "downgrade" in specs? Is this a mistake?** Explain the concept of **"Provisioned vs. Utilized"** capacity in your answer and why this distinction is critical for cloud cost savings.

---

### Critical Thinking Question 3

You are managing a complex migration involving both applications and databases. You are logged into the **AWS Migration Hub** console to track the status.

You notice that one specific database migration (which is being handled by the **AWS Database Migration Service - DMS**) has failed with an error.

**Can you debug the error logs or restart the specific DMS migration task directly from within the Migration Hub interface?**

Explain the **architectural relationship** between Migration Hub and the actual migration tools (like DMS or AWS Application Migration Service) that dictates your answer.