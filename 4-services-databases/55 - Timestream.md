#AWS-SAA
Theory: https://gemini.google.com/share/40cf507f8cbd
Architect: https://gemini.google.com/share/fe767d1ff7cd

---
**Question 1**

The text highlights that traditional databases suffer from "performance bottlenecks" with high-volume streams, whereas Timestream **"decouples data ingestion, storage, and querying, allowing each component to scale independently."**

**Why is this "decoupled" architecture so critical for an IoT application specifically?**

---

**Critical Thinking Question 2:**
   
AWS Timestream automatically moves data from an **In-Memory Store** to a **Magnetic Store** based on policies you define.

**Analyze the access patterns of time-series data (e.g., monitoring a server's CPU usage). Why is this specific dual-store approach (Memory + Magnetic) economically and technically superior to keeping everything in one high-performance storage tier?**

---
**Critical Thinking Question 3:**

In a traditional Relational Database (like PostgreSQL or MySQL), if you want to start storing a new data point (e.g., adding a "Temperature" metric to a table that only had "Voltage"), you typically have to run an `ALTER TABLE` command to add a column. On a table with billions of rows, this operation can lock the table for hours, causing downtime.

**Considering a rapidly evolving IoT or DevOps environment, explain how AWS Timestream’s "Dynamic Schema" feature mitigates this risk. What actually happens when a device sends a metric that Timestream hasn't seen before?**