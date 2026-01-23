#AWS-SAA
Theory: https://gemini.google.com/share/c0ef619cb9ac
Architect: https://gemini.google.com/share/63f0a27df5c4

---

### Critical Thinking Question 1

You are the Lead Architect for a migration project involving a "Black Box" legacy application. The original developers left years ago, and there is zero documentation. You know the application consists of 10 servers, but you have no idea which server talks to which, or which specific background services are critical.

Your Project Manager suggests using **Agentless Discovery** because it is faster to deploy (just one collector in vCenter) and doesn't require getting approval to install software on the production Linux kernels.

**Why might this "easier" choice be a catastrophic mistake for this specific "Black Box" scenario?**

In your answer, explain precisely **what level of visibility** you lose with Agentless discovery regarding **dependencies**, and why that matters when you don't know how the app works.

---

### Critical Thinking Question 2

Let's look at the security aspect.

Your CISO (Chief Information Security Officer) is reviewing the proposal to use **Agent-based discovery**. She is very concerned. She reads that the agent collects "Database metadata" and "Running processes."

She asks: _"If we install this agent on our SQL Server that holds credit card numbers, will AWS be able to read or export our actual customer records (the data rows inside the tables)?"_

**Based strictly on the "Collected Data" lists provided in the text, how do you answer her?**