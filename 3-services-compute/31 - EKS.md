#AWS-SAA
Theory: https://gemini.google.com/share/366e80d73b38
Architect: https://gemini.google.com/share/12b45658a14f

---

**Question 1**

The text outlines three ways to manage worker nodes: **Self-Managed**, **Managed Node Groups**, and **Fargate**.

It describes **Managed Node Groups** as a middle ground that "automates the lifecycle management... such as node creation, updates, and termination" while still using EC2 instances.

**Here is the challenge:** If AWS is automatically handling the "updates and termination" of your worker nodes in a Managed Node Group, this implies that nodes might be replaced or rebooted by the service (e.g., during a version upgrade or patching).

From a Solution Architect's perspective, what **specific architectural characteristic** must your application possess to run safely on Managed Node Groups?

---

**Question 2**

Let's look at the third option: **Fargate**.

The text states: _"Fargate offers a serverless computing model... eliminating the need to manage EC2 instances altogether."_

This sounds perfect for reducing operations. However, in a standard Kubernetes cluster (using EC2 worker nodes), it is common to run **DaemonSets**. A DaemonSet ensures that a copy of a specific Pod runs on **every single node** in the cluster (e.g., a log collector like Fluentd, or a security agent that scans the node's OS).

**Here is the challenge:** If you choose to run your application purely on **Fargate**, what happens to the concept of a DaemonSet? Why might a security team that relies on installing OS-level agents on every node strictly forbid you from using Fargate?

---

**Question 3**

Let's shift our focus to the **Control Plane**.

The text says: _"EKS takes care of the provisioning, scaling, and management of the Kubernetes control plane components... these critical components are complex to configure manually."_

In a traditional "Self-Hosted" Kubernetes setup (where you build it yourself on bare EC2s, not using EKS), you have to run 3 separate EC2 instances just for the Control Plane (for High Availability) and pay for those instances.

**Here is the challenge:** AWS charges a flat hourly fee (approx $0.10/hour or $72/month) for the EKS Control Plane. Imagine you are a startup architect trying to save money. You only need a very tiny cluster for development (maybe just 1 worker node).

Why might the **EKS Control Plane** pricing model actually be **more expensive** for a tiny dev cluster compared to a manual setup on a single small EC2? But conversely, why does that flat fee become a "steal" (extremely cheap) when you are running a massive enterprise cluster with 1,000 nodes?

---

**Question 4 (Final Critical Thinking Question)**

The text mentions using **Infrastructure as Code (IaC)** (like Terraform or `eksctl`) versus the **AWS Console**.

_"Leveraging Infrastructure as Code... ensures consistency and version control."_

Imagine you are the Lead Architect for a bank. You have a strict compliance requirement: **"No human is allowed to manually change the production environment."**

**Here is the challenge:** How does adopting IaC strictly enforce this "No Ops" policy? Specifically, if a junior engineer manually changes a Security Group rule in the AWS Console to "fix a bug" quickly, what happens the next time you run your IaC deployment pipeline? Why is this "correction" critical for security?