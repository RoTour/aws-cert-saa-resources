#AWS-SAA
Theory: https://gemini.google.com/share/0b64a2276209
Architect: https://gemini.google.com/share/89cf757e3362

---

### Question 1

The text emphasizes **"Dynamic Scalability"** where AWS automatically provisions and scales copies of your code to handle traffic surges (like holiday shoppers).

Based on this mechanism, here is the question:

**If one specific execution of your Lambda function saves a user's session data (like a shopping cart ID) to a local variable or a local file on the instance, can the _next_ execution of that function (triggered by the same user a second later) reliably access that data?**

Explain **why or why not** based on how Lambda handles the underlying infrastructure.

---

### Question 2

The text mentions that AWS Lambda "scales your application automatically, handling increased traffic effortlessly."

As a Solutions Architect, you know that "infinite scale" is marketing language, not reality.

There is a mechanism called **Concurrency Limit** (default is usually 1,000 concurrent executions per region).

**Scenario:** You have a Lambda function behind **Amazon API Gateway** (Synchronous) and another triggered by **S3 Uploads** (Asynchronous). You suddenly hit 5,000 concurrent requests, blowing past your limit.

**How does the failure experience differ for the user uploading to S3 versus the user calling the API Gateway?** (Think about: Does the user get an error immediately? Does the system retry?)

---

### Question 3

Now, let's look at **Performance & Cost**.

In AWS EC2, you pick an instance type (e.g., `t3.large`) which gives you a specific amount of CPU and specific amount of RAM.

In AWS Lambda, there is **only one** slider you can adjust in the console: **Memory (RAM)** (from 128 MB to 10 GB). You cannot directly select CPU speed.

**If you have a CPU-intensive task (like strict number crunching) that barely uses any RAM, why would you still advise increasing the _Memory_ setting?**