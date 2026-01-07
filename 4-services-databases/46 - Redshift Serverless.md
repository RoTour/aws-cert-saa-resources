#AWS-SAA
Theory: https://gemini.google.com/share/a90676708e87
Architect: https://gemini.google.com/share/f4160a27926c

---

**Question 1** Redshift Serverless is marketed as a cost-saving solution because it stops billing you when your queries stop (auto-pause) and scales down when load is light.

However, consider a **"Steady-State" scenario**: An automated factory system runs optimization queries _every single second of the day, 24/7/365_, maintaining a constant, flat compute load equivalent to 128 RPUs. It never idles.

**Why would switching to Redshift Serverless likely _increase_ your monthly bill in this specific scenario compared to a traditional Provisioned Cluster (especially one using Reserved Instances)?**

---

**Question 2** The text states: _"Adjusting the base capacity directly influences query performance, particularly for resource-intensive data processing tasks."_

Imagine you are running a **single**, extremely heavy query that needs to sort 1 TB of data in memory. You have two Redshift Serverless workgroups:

- **Workgroup A:** Base RPU = 8 (Minimum)
- **Workgroup B:** Base RPU = 512 (Maximum)

Since Redshift Serverless "automatically scales," a common misconception is that both workgroups will just "scale up" to meet the demand and finish at the same time.

**According to the text, why will Workgroup A likely perform significantly worse for this single heavy query than Workgroup B?**

---

**Question 3** The text mentions **Max Capacity** as a way to "control costs" by setting limits on usage (daily, weekly, monthly).

Imagine you set a strict **Daily Max Capacity** of 100 RPU-hours to stay within budget. It's Black Friday. Traffic surges. At 2:00 PM, your automated dashboard triggers a massive report that consumes the last of your daily budget.

**What happens to your Data Warehouse at 2:01 PM when the CEO tries to run a critical revenue query?**
