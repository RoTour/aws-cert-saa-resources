#AWS-SAA
Theory: https://gemini.google.com/share/69083a992c50
Architect: https://gemini.google.com/share/692840cf20a1

---

### Critical Thinking Question 1

The text distinguishes between **Multi-AZ Deployments** and **Read Replicas**.

Imagine a junior developer on your team suggests: _"Since a Read Replica creates a copy of the data and can be promoted to a primary instance if needed, we shouldn't pay extra for Multi-AZ. We can just use the Read Replica as our High Availability (HA) solution."_

**Critique this strategy.** Specifically, explain why a Read Replica is **not** a direct substitute for Multi-AZ when the primary goal is **automatic** recovery and **data integrity** during a sudden infrastructure failure.

---

### Critical Thinking Question 2

Let's move to **Performance and Scaling**.

You are monitoring your production RDS database. The CloudWatch dashboard shows the **CPU utilization is consistently hitting 95%**, causing the application to slow down.

Your manager suggests: _"Let's just add a Read Replica to fix the load."_

**In what specific scenario would adding a Read Replica completely FAIL to lower the CPU load on the primary instance?**

---

### Critical Thinking Question 3

Let's discuss **Storage Performance**.

The text describes **General Purpose SSD (gp2/gp3)** as "cost-effective" and capable of "bursting," while **Provisioned IOPS (io1/io2)** offers "consistent throughput."

Imagine you are running a financial reporting database. It runs quietly for most of the month, but on the last day of the month, it runs a massive, complex report that hammers the disk continuously for 8 hours.

You decide to save money by using **General Purpose SSD** because the peak IOPS required (say, 3,000 IOPS) is technically within the "burst" limit of the drive.

**Why might this decision lead to a sudden performance crash halfway through that 8-hour report?**.