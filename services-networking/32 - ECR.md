#AWS-SAA
Theory: https://gemini.google.com/share/c9ea1112114c
Architect: https://gemini.google.com/share/d58182650bfc

---

**Question 1**

The text mentions that ECR works with "ECS, EKS, or an on-premises environment" and that "authentication is required."

When you are inside AWS (like on an EC2 instance), you can attach an **IAM Role** to the instance, giving it magical permission to talk to ECR without typing a password.

**Here is the challenge:** If you are working from your **local laptop** or an **on-premise server** (which does not have an IAM role attached), how exactly do you authenticate your Docker client to ECR? Docker itself doesn't know what "AWS IAM" is; it only understands standard usernames and passwords.

How does AWS bridge this gap so standard Docker tools can log in to a private ECR repo? (Hint: It involves the AWS CLI).

---

**Question 2**

The text discusses **Lifecycle Policies** as a way to "automate image retention... optimizing storage costs," and also mentions **CI/CD pipelines** that build images automatically.

**Here is the challenge:** Imagine your CI/CD pipeline builds a new Docker image every time a developer commits code (potentially 20 times a day). You tag these images with the git commit hash (e.g., `myapp:a1b2c3d`).

After 6 months, you have 3,000 images. You want to save money, so you create a Lifecycle Policy to **"Delete any image older than 30 days."**

Suddenly, your Production environment crashes. It tries to auto-scale, but it fails because the image it was trying to pull (which was deployed 40 days ago and is very stable) has been deleted by your policy.

How should you have designed your **Tagging Strategy** and **Lifecycle Policy** to delete the "junk" development images but strictly protect the "stable" Production image, even if it is old?

---

**Question 3 (Final Critical Thinking Question)**

The text highlights **Public ECR Repositories** ("data transfer out... is free") versus **Private ECR Repositories** ("AWS charges for both storage and data transfers").

Let's say you are building a proprietary AI model. The Docker image is massive (10GB). Your team of 50 data scientists needs to pull this image to their local laptops every morning to run experiments.

**Here is the challenge:** A junior engineer suggests: _"Hey, why don't we put this image in a **Public ECR** repo? It's still secure because we can just keep the URL secret, and we'll save thousands of dollars on data transfer fees since the text says public egress is free!"_

Why is this a **catastrophic security failure** even if the URL is "secret"? And from a purely functional standpoint, what feature of Private Repositories (mentioned in the text regarding "scanning") might you lose or expose publicly?
