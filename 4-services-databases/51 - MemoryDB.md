#AWS-SAA
Theory: https://gemini.google.com/share/45a67d243a8c
Architect: https://gemini.google.com/share/b61a2e681516

---

**Question 1**

The text mentions a specific performance difference: **MemoryDB** has "low single-digit millisecond" write latency, whereas **ElastiCache** typically boasts "microsecond" write latency.

**Why is MemoryDB slower at writing data than ElastiCache?**

Explain exactly what happens during a `SET` (write) command in MemoryDB that _doesn't_ happen in ElastiCache, and explain why this extra step is non-negotiable for MemoryDB to claim the title of a "Primary Database."

---

**Critical Thinking Question 2**

The text distinguishes between **Replica Nodes** and **Shards**.

Imagine you have a MemoryDB cluster with **1 Shard** (containing 1 Primary and 3 Replicas).

**The Problem:** Your monitoring shows that your application is hitting the **Write Throughput limit** of the cluster. The CPU on the Primary node is at 100% strictly due to incoming `SET` commands.

**The Proposal:** Your colleague suggests: _"Let's add 2 more Replica nodes to this Shard. That will give us more CPU power to handle the writes."_

**Why will this fail?** Explain why adding Replicas does zero to help with Write limits, and tell me exactly what you must do to the cluster structure to fix this.
