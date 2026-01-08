#AWS-SAA
Theory: https://gemini.google.com/share/8ccaf4f1859e
Architect: https://gemini.google.com/share/a5aeff9575e8

---

**Question 1**

The provided text highlights how ElastiCache improves read performance by serving data from memory rather than disk. However, as a Solutions Architect, you must always evaluate trade-offs.

When you introduce a caching layer like ElastiCache between your application and your database, what is the primary risk introduced regarding data integrity?

Specifically, explain what happens (or fails to happen) in the cache when a successful write or update operation occurs on the backend database, and why this discrepancy is a critical architectural challenge.

---

**Critical Thinking Question 2**

The resource highlights that **Redis** supports "Data Persistence" (saving memory to disk), whereas **Memcached** is purely in-memory and volatile.

**Critical Challenge:** Since a cache is just a copy of data that already exists safely in your Database, why would we ever care about **Data Persistence** in the cache layer?

If the Redis node crashes and restarts, we could technically just fetch the data from the database again. **Describe a specific scenario where losing all your cache data instantly (a "Cold Cache") would be catastrophic for your application, effectively forcing you to choose Redis over Memcached.**

---

**Critical Thinking Question 3**

The text mentions two distinct scaling features for Redis: **Read Replicas** and **Data Partitioning (Sharding)**.

Imagine you are managing a popular social media app. Your ElastiCache Redis cluster currently has **one Primary node and two Read Replicas**.

**The Problem:** Your monitoring dashboard shows that the **Write CPU** on the Primary node is hitting 95%, and you are running out of **Memory (RAM)** because you are caching so many user profiles.

**The Question:** A junior engineer suggests: _"Let's just add 5 more Read Replicas to the cluster! That will fix the memory issue and lower the CPU load."_

**Why is the junior engineer wrong?** Explain why adding Read Replicas will **not** solve a "High Write" or "Out of Memory" problem, and tell me which ElastiCache feature you should use instead.