#AWS-SAA
Theory: https://gemini.google.com/share/f02a02fd8b6a
Architect: https://gemini.google.com/share/c050236590d4

---

### Question 1

Since SAM templates are ultimately transformed into CloudFormation templates before deployment, **what is the specific architectural or operational advantage of using SAM over writing raw CloudFormation templates directly?** Why introduce this extra abstraction layer if the destination is the same?

---

### Question 2

In the workflow, we run `sam package` before `sam deploy`. This step uploads your code to an S3 bucket.

**Why is this "upload to S3" step strictly necessary? Why can't CloudFormation just read the code directly from your local laptop folder during deployment?**

---

### Question 3

Let's look at the **Serverless Application Repository (SAR)**.

Imagine you find a popular image-processing application on the SAR created by another company. You decide to click "Deploy" to use it in your project.

**Who pays for the Lambda execution costs and storage costs when that application runs: the company that published it, or you? Explain why, based on the deployment mechanism.**