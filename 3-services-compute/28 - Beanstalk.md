#AWS-SAA
Theory: https://gemini.google.com/share/9869246008e7
Architect: https://gemini.google.com/share/d43012ada515

---

**Critical Thinking Question 1:**

The text emphasizes that Elastic Beanstalk "abstracts the complexity" of infrastructure by provisioning resources (like EC2 instances, Load Balancers, and Security Groups) on your behalf.

As a Solutions Architect, you must often balance **convenience** with **control**.

Does this abstraction mean you strictly _lose_ access and visibility to these underlying resources? For example, if you needed to debug a strange issue, could you still find and access the specific EC2 instance created by Elastic Beanstalk in the EC2 console, or is it a "black box" completely hidden from you?

**Explain your reasoning on how Elastic Beanstalk relates to the underlying resources it creates.**

---

**Critical Thinking Question 2:**

The text states: _"Elastic Beanstalk introduces the concept of environments... You can create separate environments for development, staging, and production."_

Imagine you have a **Production** environment serving thousands of users and a **Development** environment where you are testing a buggy new feature.

From an infrastructure perspective, how "isolated" are these environments really?

If your buggy code in the **Development** environment causes the CPU to spike to 100% and crashes the servers, does this impact the performance or stability of your **Production** environment? Why or why not?

---

**Critical Thinking Question 3:**

The text mentions that Elastic Beanstalk handles "databases (RDS)... if needed."

When you configure an environment, you can ask Elastic Beanstalk to create an RDS database _within_ that environment.

Consider the **Lifecycle** of resources. When you decide to **terminate** (delete) an Elastic Beanstalk environment (perhaps you are finished with that specific 'Test' environment), Elastic Beanstalk cleans up and deletes all the resources it created for that environment.

**What happens to the data in that RDS database?**

As an architect, is defining the database _inside_ the Elastic Beanstalk environment configuration considered "Production Best Practice"? Why or why not?