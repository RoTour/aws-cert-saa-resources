#AWS-SAA
Theory: https://gemini.google.com/share/6c0b2c5bbb34
Architect: https://gemini.google.com/share/aa5ee96e3e7d

---

### **Question 1**

You are a Lead Architect for a multi-account organization.

- **Account A** contains a central S3 bucket with processed financial data.
    
- **Account B** has an EC2 instance that needs to read this data to generate reports.
    

You have correctly attached an **IAM Policy** to the EC2 instance's role in **Account B** that allows `s3:GetObject` on the bucket in **Account A**. However, the EC2 instance is still getting an "Access Denied" error.

**What is missing from a security standpoint in Account A, and why is this different from how you would handle this if both the EC2 and the bucket were in the same account?**

---

### **Question 2 (Critical Thinking)**

Now, let’s look at a "Deny" scenario.

Your security team has a strict requirement: **"No data should ever be deleted from the 'Audit-Logs' bucket, not even by the administrator who created it."**

You decide to add a statement to the **Bucket Policy** that looks like this:

- **Effect:** Deny
- **Principal:** `*`
- **Action:** `s3:DeleteObject`
- **Resource:** `arn:aws:s3:::Audit-Logs/*`

**Two weeks later, the Root user of the account logs in and tries to delete a file. Will the Root user succeed? Why or why not?** _(Think carefully about the power of the 'Deny' effect in AWS!)_


---

### **Question 3 (The "Ultimate Protection" Challenge)**

Since we found that Bucket Policies and Versioning can still be bypassed by a determined Root user or Administrator, let's look at the "Solution Architect" way to solve this.

There is a specific AWS S3 feature (often called a **WORM** model—Write Once, Read Many) designed for legal and financial compliance. Once this is turned on in "Compliance Mode," **NO ONE**—not even the Root user, and not even AWS Support—can delete the objects until the retention period expires.

**Do you remember the name of this feature, and what is the specific "Mode" called that locks out even the Root user?**