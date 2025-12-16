#AWS-SAA
Theory: https://gemini.google.com/share/62fb7a54dd34
Architect: https://gemini.google.com/share/5c5ebf426855

---

**Critical Question 1**

The text mentions that EBS volumes are "independent" of the EC2 instances they are attached to, yet they are also subject to specific Availability Zone (AZ) constraints.

Explain the architectural implication of this "independence" regarding the lifecycle of data versus the lifecycle of compute. Specifically, if an EC2 instance is terminated, what happens to the data on the attached EBS volume, and why does the AZ constraint matter in a recovery scenario where the original instance is gone?

---

**Critical Question 2**

The text highlights two main categories of storage: **SSD** (Solid State Drive) and **HDD** (Hard Disk Drive).

Imagine you are designing a solution for a **Big Data analytics application** that processes massive log files. The processing job reads data sequentially (from start to finish) rather than jumping around to random locations.

**Why would a Solutions Architect recommend a Throughput Optimized HDD (st1) volume over a General Purpose SSD (gp3) for this specific workload?**

---

**Critical Question 3:**

Now, let's flip the scenario.

Imagine you are architecting the storage for a **high-frequency trading platform**. This application processes thousands of small buy/sell orders every second. Each order is tiny (just a few bytes), but they happen rapidly and randomly.

Which metric is the priority here—**IOPS** or **Throughput**—and consequently, which volume type from the list (gp3, io2, st1, sc1) would be the **least** suitable for this?