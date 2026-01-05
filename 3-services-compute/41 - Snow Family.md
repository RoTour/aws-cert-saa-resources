#AWS-SAA
Theory: https://gemini.google.com/share/426fe4a06430
Architect: https://gemini.google.com/share/aa82728ea30c

---

### Question 1

The article highlights that Snowcone allows you to run compute services (like **AWS Lambda** and **Amazon EC2**) directly on the device itself.

Imagine you are designing a solution for a remote mining site with very limited, intermittent satellite connectivity. Why is this **"Edge Computing"** capability (running code on the device) critical?

Specifically, what problem does processing data _locally_ solve that simply collecting all the raw data and processing it later in the AWS Cloud would not?

---

### Question 2

The article mentions that the Snowcone has **"built-in encryption using AWS Key Management Service (KMS)"** and a **"Trusted Platform Module (TPM)."**

Let's imagine a worst-case scenario: You have loaded confidential financial records onto the Snowcone and shipped it back to AWS. During transit, the delivery truck is hijacked, and the device is stolen.

Based on the features mentioned, **why is the thief unable to access your data?** specifically, what role does the **TPM** play in this security model versus the **KMS** encryption?

---

### Question 3

The workflow describes: **Order -> Configure -> Copy Data -> Ship -> AWS Uploads -> Wipe.**

As a Solution Architect, you need to plan for **Data Consistency**. You order a Snowcone to migrate 5 TB of database backups. It takes you 3 days to copy the data, 2 days to ship it, and 1 day for AWS to upload it. That is a **6-day gap**.

During those 6 days, your business is still running and generating _new_ data.

**How does this "offline transfer" model impact your database migration strategy?** What problem does this time gap create, and can you think of a high-level strategy to handle the data generated _after_ you shipped the device?