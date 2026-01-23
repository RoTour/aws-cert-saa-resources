#AWS-SAA
Theory: https://gemini.google.com/share/297ec78b7467
Architect: https://gemini.google.com/share/c83d0325c36e

---

### Critical Thinking Question 1

You are migrating a massive **10TB Database Server** from your on-premises data center to AWS. The replication phase takes 2 weeks to complete over your Direct Connect link.

During these 2 weeks, the data is being copied to the **Staging Area**.

**Question:** Are you paying for a "massive" EC2 instance (e.g., `r5.24xlarge`) in the Staging Area during these 2 weeks? Why or why not?

---

### Critical Thinking Question 2

You are migrating a critical Financial Application.
- **Friday 5:00 PM:** You install the MGN Agent on the source server. Replication starts.
- **Friday 10:00 PM:** Initial sync reaches 100%. The status is "Healthy."
- **Saturday 9:00 AM:** A user logs into the _source_ application and adds a new transaction record (Transaction #999).

**Question:** If you launch a **Test Instance** in AWS on **Saturday at 9:05 AM**, will Transaction #999 be present in the cloud database?
