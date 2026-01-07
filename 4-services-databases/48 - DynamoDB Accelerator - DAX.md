#AWS-SAA
Theory: https://gemini.google.com/share/85d2a20fec15
Architect: QUIZ_LINK

---

### Critical Thinking Question #1

The lesson mentions that DAX uses a **"write-through"** caching mechanism to ensure data consistency.

Imagine you have an e-commerce application.

1. **Scenario A:** Your application updates a product price using the **DAX client**. Immediately after the write confirms, the application reads that product's price again using the **DAX client**.
2. **Scenario B:** A separate backend process (like a Lambda function) updates a product price directly on **DynamoDB** (bypassing DAX). Immediately after, your main application tries to read that product's price using the **DAX client**.

**Question:** In each scenario, will the application see the _new_ price or the _old_ price? Explain **why** based on how DAX handles writes and cache invalidation.

---

**Question**
text
