#AWS-SAA
Theory: https://gemini.google.com/share/0dfd11eb296a
Architect: https://gemini.google.com/share/89948f4d546d

---

### Question 1

You are acting as a Solution Architect for a highly regulated company. The security team has a strict requirement: **You must install a specific custom security agent directly on the host Operating System** (the underlying server), not just inside the Docker containers. This agent needs to monitor the kernel for compliance.

Based on the distinction between **EC2 Launch Type** and **Fargate** provided in the text:

**Which launch type must you choose, and why?**

---

### Question 2

Let's look at **Cost and Efficiency**.

Imagine you are building a microservice for a news website. The traffic is extremely unpredictable:

- At 3:00 AM, there is almost zero traffic.
- At 9:00 AM, traffic spikes massively due to breaking news.
- The spikes are short-lived.

You want to avoid paying for idle CPU time when the site is quiet, and you want to avoid the administrative overhead of constantly patching servers.

**Based on the "Summary Comparison" in the text, which launch type is the better fit here, and exactly how does its pricing model benefit this specific scenario?**

---
### Question 3

Let's look at **Availability and the Role of the ECS Service**.

Your colleague has set up an application on ECS.

- They created an **ECS Service** and configured it to run **4 Tasks** (replicas) of the application at all times.
- They deployed all 4 tasks onto a **single EC2 Instance**.

Referencing the **"Challenges with Containers"** section of the text:

**1. Is this setup considered "Highly Available"? Why or why not?** 
**2. If that single EC2 instance suffers a hardware failure and dies, what exactly happens to your 4 tasks, and what will the ECS Service _try_ to do?**
