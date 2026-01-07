#AWS-SAA
Theory: https://gemini.google.com/share/85d2a20fec15
Architect: https://gemini.google.com/share/af7903584679

---

### Critical Thinking Question #1

The lesson mentions that DAX uses a **"write-through"** caching mechanism to ensure data consistency.

Imagine you have an e-commerce application.

1. **Scenario A:** Your application updates a product price using the **DAX client**. Immediately after the write confirms, the application reads that product's price again using the **DAX client**.
2. **Scenario B:** A separate backend process (like a Lambda function) updates a product price directly on **DynamoDB** (bypassing DAX). Immediately after, your main application tries to read that product's price using the **DAX client**.

**Question:** In each scenario, will the application see the _new_ price or the _old_ price? Explain **why** based on how DAX handles writes and cache invalidation.

---

### Critical Thinking Question #2

Building on that discussion about consistency:

DynamoDB allows developers to request **Strongly Consistent Reads** (guaranteeing you get the absolute latest data committed to the database). DAX, however, is an _eventually consistent_ cache by default.

**Question:** If your application uses the **DAX client** and issues a `GetItem` request specifically asking for a **Strongly Consistent Read**:
1. Does DAX serve this request from its cache?
2. If not, how does DAX handle the request?


---

### Critical Thinking Question #3

The resource emphasized that DAX is designed to boost **read performance** (up to 10x) and reduce **read load** on DynamoDB. It also mentioned the "write-through" mechanism where data is written to both the cache and the database.

**Question:** Consider an application with a **Write-Heavy** workload (e.g., an IoT sensor logging temperature every second, but that data is rarely read, or perhaps only read once significantly later).

Would adding DAX to this specific architecture **improve**, **degrade**, or have **no impact** on the application's overall performance (latency and throughput)?