#AWS-SAA
Theory: https://gemini.google.com/share/cf467fe671ba
Architect: https://gemini.google.com/share/ff257550cfb2

---

**Critical Thinking Question 1**

The text highlights a specific concept called **"Readiness Checks"** (used by the Recovery Controller) and distinguishes them from standard monitoring.

In your own words:

1. **How is a "Readiness Check" conceptually different from a standard "Health Check"** (like one a Load Balancer performs on an active instance)?
    
2. **Why is this distinction specifically critical for a standby site** that is _not_ currently taking any traffic?
    

(Take your time. I want to see how you distinguish "functioning" from "ready.")

---

### Critical Thinking Question 2

Let's move from **Compute** (servers) to **Data** (database).

The text specifies using a **Global DynamoDB table** that spans both regions.

Imagine we designed the architecture differently:

- **Active Site (Region A):** Connected to `Table-A` (Local).
    
- **Standby Site (Region B):** Connected to `Table-B` (Local).
    
- There is **no** connection between Table A and Table B.
    

If Region A fails and we successfully route all traffic to Region B:

**What is the immediate problem the users will face regarding their account history or saved data?**
