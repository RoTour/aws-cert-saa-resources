#AWS-SAA
Theory: https://gemini.google.com/share/011acdfd8eca
Architect: https://gemini.google.com/share/63f23138933f

For commands see [[linux file system mount volume AWS EFS commands]]

---

### Critical Thinking Question 1

The text explains that Amazon EFS is a regional service (implied by "Standard" storage classes offering multi-AZ resilience) and that you must create **Mount Targets** in your subnets to connect to it.

**Here is the question:**

If the EFS data itself is durable and replicated across multiple Availability Zones (AZs) by default (in Standard mode), why is it strictly necessary to create a **Mount Target** in _every_ AZ where you have EC2 instances?

Specifically, if you have a fleet of web servers running in **Availability Zone A** and **Availability Zone B**, but you only create a Mount Target in **Availability Zone A**, what are the consequences for the instances in Zone B? Can they still access the file system? Explain the networking limitation here.

---

### Critical Thinking Question 2

Let's move to **Performance Modes**. This is a common area of confusion for architects.

**Scenario:** You are designing a solution for a media processing company. They have a fleet of 50 EC2 instances that need to process **millions of very small thumbnail images** stored on EFS.

They launch the system using **General Purpose** performance mode (the default). However, they notice that while their total data throughput (MB per second) is actually quite low, the application is running slowly. The CloudWatch metrics show the file system is hitting a specific limit, even though they aren't transferring massive amounts of data.

**The Question:** Why is the **General Purpose** mode struggling with "millions of small files" specifically? What is the technical bottleneck here (it is not bandwidth), and why would switching to **Max I/O** mode resolve this?

---

### Critical Thinking Question 3

The text concludes with a very specific warning: _"EFS... is not a substitute for block storage solutions like EBS, especially when used for booting operating systems."_

**Here is the question:**

Technically, EFS is just storage, and your EC2 instance has network access to it. Why, specifically, can an EC2 instance **not** boot its Operating System (like the root C: drive or `/` root partition) from an EFS volume?

Think about the "chicken and egg" problem regarding the network and the operating system startup process.
