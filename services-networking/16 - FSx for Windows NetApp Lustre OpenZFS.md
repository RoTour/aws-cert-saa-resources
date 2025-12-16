#AWS-SAA
Theory: https://gemini.google.com/share/712c1bae795c
Architect: https://gemini.google.com/share/a37225411092

---

### Critical Thinking Question 1

The text mentions that **Amazon FSx for Lustre** is deeply integrated with **Amazon S3** and is often used for high-performance workloads like machine learning.

**Here is the question:**

Architecturally, why is FSx for Lustre typically used as a "temporary" or "scratch" file system rather than a permanent long-term storage solution?

Specifically, look at the **Deployment Options** section of the text. What inherent infrastructure limitation does **FSx for Lustre** have compared to the other FSx flavors (Windows, NetApp, OpenZFS), and how does that limitation threaten the **High Availability (HA)** of your data if you were to store it there permanently?
