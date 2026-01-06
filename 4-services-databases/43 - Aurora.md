#AWS-SAA
Theory: https://gemini.google.com/share/81f703a079f6
Architect: https://gemini.google.com/share/64648435b17b

---

### Critical Thinking Question 1

The text states that Aurora stores **6 copies** of your data across 3 Availability Zones (2 copies per zone). In standard computer science, writing data to 6 different hard drives usually takes much _longer_ than writing to just 2 (like in standard RDS Multi-AZ).

**Why is Aurora's "Write" performance faster than standard RDS Multi-AZ, despite having to update 3 times as many copies?**

---

### Critical Thinking Question 2

Let's look at **Aurora Serverless**.

The text says Aurora Serverless "automatically scales capacity... based on application load" and is ideal for "unpredictable capacity requirements."

Imagine you are running a flash sale application. You expect 0 users at 8:59 AM and 100,000 users at 9:00 AM sharp.

**Why might Aurora Serverless (specifically v1) potentially FAIL or cause errors during that specific 1-minute window from 8:59 to 9:00?**

---

### Critical Thinking Question 3

Now, imagine a scenario where a specific **segment of physical storage** (one of the SSDs holding your data) becomes corrupt or fails completely.

In a traditional database (where each instance has its own disk), you would failover to the Replica because the Replica has a _separate_ healthy disk.

**In Aurora, since the Replica is looking at the exact same "Shared Volume" as the Primary, why doesn't a storage corruption affect BOTH instances and take down the entire cluster?**
