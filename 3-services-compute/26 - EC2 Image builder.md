#AWS-SAA
Theory: https://gemini.google.com/share/edbfddc271c8
Architect: https://gemini.google.com/share/90476503643f

---

### Question 1

We established that a "Golden Image" contains pre-installed software and configurations. An alternative approach in AWS is "bootstrapping," where you take a plain base image (like a generic Amazon Linux AMI) and install all your software when the instance first launches (typically using EC2 User Data scripts).

**From an architectural perspective, what is the primary trade-off between "baking" your software into a Golden Image versus "bootstrapping" it at launch?**

---

**### Critical Thinking Question 2

However, imagine you have a Golden Image that you built 6 months ago. It has the operating system and your application baked in. Today, a critical security vulnerability is discovered in the OS kernel.

**In a "Golden Image" strategy, what specific operational challenge does this scenario create compared to the "Bootstrapping" method, and what does this imply about how often you need to run your Image Builder pipeline?**

---

### Critical Thinking Question 3

So, we have established that to keep Golden Images secure, we must automate the pipeline to rebuild them frequently (perhaps every week).

But automation creates a new risk. Imagine a scenario where a new OS patch is released, but it contains a bug that crashes your specific application.

**If your EC2 Image Builder pipeline is set to run automatically every Monday morning, what specific mechanism within the pipeline prevents this broken image from being shared to your production accounts and taking down your website?**