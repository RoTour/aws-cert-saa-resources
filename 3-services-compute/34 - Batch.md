#AWS-SAA
Theory: https://gemini.google.com/share/f6b6daa7e65c
Architect: https://gemini.google.com/share/1eec0399a023

---

### Question 1

In AWS Batch, you have **Job Queues** and **Compute Environments**.

**Why does AWS decouple these two concepts instead of just having you submit jobs directly to a Compute Environment?**

---

### Question 2

AWS Batch allows you to use **EC2 Spot Instances** in your Compute Environment.

**What is the specific risk introduced by using Spot Instances for a batch job, and how does AWS Batch handle that risk if it materializes?**

---

### Question 3

Let's look at the **Job Definition** component.

The material states that a Job Definition acts as a "template." However, when you submit a job, you can provide **Parameter Overrides**.

**Why is this override capability critical for a "batch" workflow? Give me a concrete example where you would use the _same_ Job Definition but _different_ overrides for 1,000 distinct jobs.**

---

### Question 4

Let's test your understanding of the **Lifecycle** combined with **Resource Limits**.

The text states that AWS Batch "queues jobs until the necessary resources are available."

Imagine you have a Compute Environment with a hard **Maximum vCPU limit of 10**. You submit **2 jobs**:

- Job A requires 8 vCPUs.
    
- Job B requires 4 vCPUs.
    

Job A starts running first.

1. **What specific lifecycle state** will Job B sit in while Job A is running?
    
2. **Why** doesn't AWS Batch just launch another EC2 instance to run Job B immediately?