#AWS-SAA
Theory: https://gemini.google.com/share/2d0400116d69
Architect: https://gemini.google.com/share/ec1696788960

---

**Question 1**

The text states that the "Cluster Volume" replicates your data **six ways across three Availability Zones**.

**Why is this architecture significant for a "Primary" instance failure?**

Specifically, if your Primary instance (EC2) crashes and a Replica is promoted to replace it, **does the new Primary need to copy or move any data before it can start accepting writes?** Why or why not? Explain how the "Shared Storage" model works here.

---

**Critical Thinking Question 2**

You mentioned that the storage is shared. However, each Instance (Primary and Replicas) still has its own **CPU and RAM (Memory)**.

**The Scenario:** A user updates their profile picture. The request hits the **Primary** instance, which writes the change to the Cluster Volume. The write is successful. One millisecond later, the same user refreshes their profile page. This read request is routed to a **Replica** instance (using `secondaryPreferred`).

**The Problem:** Despite the "Shared Storage," it is possible for the user to see their **old** profile picture for a brief moment (Replica Lag).

**Why?** If they share the same disk, why doesn't the Replica "see" the new picture instantly?
