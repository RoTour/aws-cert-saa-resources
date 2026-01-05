#AWS-SAA
Theory: https://gemini.google.com/share/3d6c2cc7d45b
Architect: https://gemini.google.com/share/92952a943342

---

**Question 1**

The text outlines two deployment methods: **Source Code Deployment** (where AWS builds the code for you) and **Container Image Deployment** (where you build the image and AWS just runs it).

"Source Code Deployment" sounds amazing because it removes the need to write a Dockerfile or configure a build pipeline.

**Here is the challenge:** Imagine you are building a Python application that uses a very specific, non-standard C++ library for video processing. This library requires you to install system-level dependencies (like `apt-get install lib-video-x`) before the Python code can be compiled.

Why would **Source Code Deployment** likely fail for this specific application? As an architect, why does switching to **Container Image Deployment** solve this problem, even though it adds more work for you?

---

**Question 2**

The text distinguishes between the **Application URL** ("accessible via a unique domain") and the **VPC Connector** ("bridges your application with private VPC resources").

**Here is the challenge:** You have deployed an internal HR tool on App Runner. You configure the **VPC Connector** to allow the app to talk to a private RDS database in your corporate VPC.

Your Security Officer looks at the setup and says: _"Great job! Since you attached it to our Private VPC, the App Runner URL is now private. People on the public internet can no longer open the website, right?"_

Based on the text's description of "public accessibility" versus "private access to resources," why is the Security Officer **wrong**? Does the VPC Connector control **Inbound** traffic (users coming to you) or **Outbound** traffic (you going to the database)?

---

**Question 3 (Final Critical Thinking Question)**

The text describes the "Automatic Deployment" feature: _"A merge into the main branch triggers the CI/CD pipeline... App Runner deploys the new image automatically."_

This is the "Continuous Deployment" (CD) dream. However, in large enterprises, you often have a strict policy: **"Nothing goes to Production on Friday afternoon."**

**Here is the challenge:** If you have "Automatic Deployment" enabled on your Production App Runner service, and a developer merges a bug fix to the `main` branch at 4:55 PM on a Friday, it _will_ deploy.

From a process/architecture standpoint, how do you architect your **Git Branching Strategy** or your **App Runner Configuration** to prevent this Friday disaster while still keeping the automation for the Development environment? (Hint: Think about using different branches or different "Services").