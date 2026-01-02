#AWS-SAA
Theory: https://gemini.google.com/share/c9ea1112114c
Architect: QUIZ_LINK

---

**Question 1**

The text mentions that ECR works with "ECS, EKS, or an on-premises environment" and that "authentication is required."

When you are inside AWS (like on an EC2 instance), you can attach an **IAM Role** to the instance, giving it magical permission to talk to ECR without typing a password.

**Here is the challenge:** If you are working from your **local laptop** or an **on-premise server** (which does not have an IAM role attached), how exactly do you authenticate your Docker client to ECR? Docker itself doesn't know what "AWS IAM" is; it only understands standard usernames and passwords.

How does AWS bridge this gap so standard Docker tools can log in to a private ECR repo? (Hint: It involves the AWS CLI).

---

**Question**
text
