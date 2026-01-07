#AWS-SAA
Theory: https://gemini.google.com/share/0f38b965ae84
Architect: https://gemini.google.com/share/7311a55a21c8

---

**Question 1** Redshift uses **columnar storage**, which is mentioned as a key feature for speeding up analytical queries (OLAP) where you aggregate data over millions of rows.

However, this same architectural choice makes Redshift significantly _less_ efficient for transactional workloads (OLTP), such as frequently updating or inserting single rows (e.g., a user changing their password or adding a single item to a cart).

**Explain _why_ this is the case from a disk I/O perspective.** Why does writing or updating a single complete record require more work in a columnar database than in a traditional row-based database?

---

**Question 2** The text describes **Massively Parallel Processing (MPP)**, where the Leader Node "delegates query operations by assigning portions of the data to each compute node."

Imagine you have a Redshift cluster with **4 Compute Nodes**. You upload a massive dataset of Sales logs. Due to a configuration choice, **90% of the data ends up stored on Node A**, while Nodes B, C, and D only hold about 3% each.

When you run a complex query (like "Calculate Total Revenue"), **how will this uneven data distribution impact the _total_ time it takes for the query to finish?**

---

**Question 3** The text states that **Redshift Managed Storage (RMS)** "utilizes high-performance SSD-based local storage as a tier-one cache" while leveraging Amazon S3 to scale to petabytes.

Imagine you have a data warehouse with **500 TB of historical data** (accessed once a year) and **10 TB of current data** (accessed every minute).

**1. Based on the description of RMS, where does the 500 TB physically reside versus the 10 TB?** 
**2. If a user suddenly runs a query on that "cold" 500 TB of historical data, what specific action must the system take before the Compute Nodes can actually process it?**

---

**Question 4** The text explains that the **Leader Node** "coordinates compute nodes and manages external communications with client applications," while **Compute Nodes** execute the queries.

Imagine you run a query that simply asks for a massive dump of raw data: `SELECT * FROM Sales_Logs` (returning 50 million rows).

Even if you have 100 powerful Compute Nodes that can read the data from disk instantly, **why might the Leader Node become a performance bottleneck in this specific scenario?**