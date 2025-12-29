#AWS-SAA
Theory: https://gemini.google.com/share/0faf7676b157
Architect: https://gemini.google.com/share/2e0ce78906f3

---

### Question 1: The "Speed" vs. "Cost" Trade-off

The text introduces two main tools: **AWS Backup** and **Elastic Disaster Recovery (DRS)**.

Imagine a CFO looks at your proposed architecture and says: _"Why do we need this 'Elastic Disaster Recovery' service? It sounds complicated. We are already taking daily snapshots with AWS Backup. If the servers crash, can't we just restore from those backups?"_

**From an architectural perspective, how would you explain the difference in "Recovery Time" (how fast you get back online) between restoring from a Backup versus failing over with DRS?**

---

### Question 2: The Cost of "Insurance"

The text mentions that Elastic Disaster Recovery (DRS) uses a **"Staging Area"** to minimize capital expenditure.

Imagine you have a massive database server with 64 vCPUs and 256GB of RAM on-premise. You want to protect it using DRS.

**Why doesn't the Staging Area in AWS cost you the same enormous price as running that massive 64-vCPU server 24/7? What exactly is running in that Staging Area while we wait for a disaster?**

---

### Question 3: The "Point in Time" Paradox

The text mentions that AWS Backup allows you to define a **"Retention Policy"** (e.g., keep backups for 30 days).

Imagine a scenario where a hacker deletes a critical table in your database on **Day 15**. You don't notice until **Day 20**.

**If your Backup Plan is set to "Daily Backup at Midnight" and "Retention: 30 Days," can you recover the data? If so, precisely what state will the database be in after recovery?**