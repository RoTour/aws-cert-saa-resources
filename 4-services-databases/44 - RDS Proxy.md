#AWS-SAA
Theory: https://gemini.google.com/share/f2620b162019
Architect: https://gemini.google.com/share/d6c08097eb12

---

**Critical Thinking Question 1:**

The documentation states that RDS Proxy reduces overhead by "pooling and sharing connections." It's easy to understand why this helps network latency (avoiding the TCP/TLS handshake), but the text specifically highlights that high connection counts lead to **CPU and Memory exhaustion** on the database itself.

**Explain the technical mechanism behind this.** Why does a database instance consume significant CPU and Memory just to _maintain_ an open connection, even if that connection is idle (not currently running a query)? Why isn't it free to just keep the door open?

---

****Critical Thinking Question 2:**

The text mentions that RDS Proxy reduces failover downtime by up to 66% for Aurora and RDS. It specifically says the proxy "automatically reconnects to the new primary instance."

**Why does this result in a faster recovery than a standard application connecting directly to the database?**

---

**Critical Thinking Question 3:**

The resource states: _"RDS Proxy integrates with AWS services like IAM... eliminating the need to hardcode credentials."_

If I am a developer writing code for a Lambda function, and I want to connect to the RDS Proxy **without** a password, **what exactly does my code send to the Proxy to prove its identity?**

---

**Critical Thinking Question 4 (Advanced):**

We know RDS Proxy works by "multiplexing" transactions—it grabs a connection from the pool, runs your query, and then puts the connection back for someone else to use.

Imagine your application runs this SQL command at the start of a session: `SET session_time_zone = 'America/New_York';`

Then, it runs a few `SELECT` queries.

**Does this behavior cause any problems for RDS Proxy's efficiency?** (Hint: Think about what happens to that specific connection in the pool after you change its settings).

---

**Critical Thinking Question 5:**

RDS Proxy is often mentioned alongside **AWS Lambda**.

In a traditional server-based app (like on EC2), you might have a long-running application that opens a connection pool (e.g., using HikariCP) at startup and keeps it open for weeks.

**Why is this "connection pool at startup" strategy fundamentally impossible or highly inefficient for AWS Lambda functions?**