#AWS-SAA
Theory: https://gemini.google.com/share/cf1a93f0f7f7
Architect: https://gemini.google.com/share/4cc75fd71a12

---

**Critical Thinking Question #1** The text highlights that organizations adopt cloud technologies for "scalability" and that AWS Outposts provides a "consistent hybrid experience" by mirroring AWS cloud operations. However, AWS Outposts is a physical rack with finite hardware installed in your specific location.

**Challenge the concept of "Elasticity" in this context.** How does the behavior of an Auto Scaling Group on an AWS Outpost differ fundamentally from an Auto Scaling Group in a standard AWS Region? Consequently, what specific architectural risk does this introduce for a "cloud-native" application deployed to an Outpost that is accustomed to infinite scaling?

---

**Critical Thinking Question #2** The text states: _"Once deployed, the Outposts system connects to the nearest AWS Region using AWS Direct Connect or a VPN."_

Let's discuss **Availability and Failure Modes.** Imagine a scenario where a construction crew accidentally cuts the fiber optic cable connecting your data center to the internet. Your connection to the AWS Region is completely severed.

**What happens to your EC2 instances running on the Outpost?** Do they immediately shut down? Can you still restart them or change their configuration? Walk me through the state of the "Data Plane" (your running app) vs. the "Control Plane" (AWS management) during this disconnection.

---

**Critical Thinking Question #3** The text mentions: _"By extending your VPC to include an Outposts subnet, instances running locally on Outposts can securely communicate with other instances in your VPC via private IP addresses."_

This sounds seamless, but let's talk about **Latency and Physics.** You have an application with a frontend on the public AWS Region (e.g., us-east-1) and a backend database running on an Outpost in your basement in France.

**Scenario:** The frontend makes a query to the backend on the Outpost. **Question:**

1. Does the traffic travel over the public internet, or does it stay entirely within the Amazon network?
    
2. If you treat this "Outpost Subnet" exactly like a regular Availability Zone (AZ) subnet in your code, what performance issue might you unexpectedly encounter?