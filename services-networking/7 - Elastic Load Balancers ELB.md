Theory: https://gemini.google.com/share/c07fee578212
Architect: https://gemini.google.com/share/e8eaa6710385

---

**Question 1:** The text highlights a significant difference in how the Application Load Balancer (ALB) and Network Load Balancer (NLB) handle encryption. The ALB terminates the SSL connection (decrypts it), while the NLB typically passes the encrypted traffic directly to the backend.

From a **security and compliance** perspective, why might an organization be _forced_ to use an NLB (or an ALB in TCP passthrough mode) instead of standard ALB SSL termination, even if they lose the "intelligent routing" features? Think about who "owns" the data.

---

**Question 2:**

Let's look at **Health Checks**. The text mentions that ALBs perform "detailed health checks" (Layer 7) while NLBs rely on TCP or ICMP checks (Layer 4).

Imagine your web application on an EC2 instance has crashed internally. The web server process (like Nginx or Apache) is still running and listening on port 80, but every request returns a `500 Internal Server Error` page because the database connection failed.

**How would an NLB likely react to this situation compared to an ALB?** Would the NLB stop sending traffic to this instance? Why or why not?

---

**Question 3:**

Let's look at **Cross-Zone Load Balancing** and Availability.

The text states: _"Without [Cross-Zone Load Balancing], a load balancer node will only route traffic to EC2 instances within its own availability zone."_

Imagine this scenario:
1. You have an ALB deployed in **Zone A** and **Zone B**.
2. Your DNS directs a specific client to the Load Balancer Node in **Zone A**.
3. Suddenly, a power outage in Zone A causes **all your EC2 instances in Zone A to fail**.
4. Your instances in **Zone B** are perfectly healthy.

If **Cross-Zone Load Balancing** is **disabled**, what happens to that client's request? Does it get served by the instances in Zone B, or does it fail?
