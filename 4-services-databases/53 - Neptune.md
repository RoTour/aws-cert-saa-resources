#AWS-SAA
Theory: https://gemini.google.com/share/ef67dea545a2
Architect: https://gemini.google.com/share/0c7beb457de7

---

### Critical Thinking Question #1

Let's assume you are designing a social networking application where users can follow each other. You need to implement a feature to "suggest friends of friends" (looking 2 or 3 degrees of separation deep).

Technically speaking, you _could_ model this in a standard Relational Database (like Amazon RDS) using tables, Foreign Keys, and SQL queries. However, the text asserts that graph databases like Neptune are significantly better for this specific use case.

**Why exactly does the performance of a relational database degrade significantly as you try to query these deep relationships (e.g., finding friends of friends of friends), and how does the underlying structure of a graph database specifically solve this performance bottleneck?**

---

### Critical Thinking Question #2

The text mentions that **Amazon Neptune Global Database** allows you to deploy a primary database in one region and replicate data to up to five secondary **read-only** clusters in different regions.

Imagine you are the Architect for a global banking app. You use this Global Database feature to serve customers in the US (Primary) and Europe (Secondary).

**If a network failure completely cuts off the US region (Primary), your European users can still _read_ their balance (because of the local read-replica). But what happens if a European user tries to _transfer money_ (a write operation)? Based on the architecture described (Primary vs. Read-Only), what must happen to the cluster architecture before that write can succeed?**

---

### Critical Thinking Question #3

The text highlights **Amazon Neptune ML** and mentions that it uses **Graph Neural Networks (GNNs)** to improve prediction accuracy (e.g., by over 50%) compared to traditional methods.

Let's apply this to **Fraud Detection**, a common use case mentioned in the text.

A traditional Machine Learning model might analyze a specific transaction row in a database: `[User_ID: 123, Amount: $5,000, Location: Nigeria, Device: iPhone]`. It looks for anomalies in these specific _values_.

**How does a Graph Neural Network (Neptune ML) analyze this transaction differently? Specifically, what "extra" information does the graph structure provide that the traditional row-based model is completely blind to?**
