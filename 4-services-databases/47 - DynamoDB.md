#AWS-SAA
Theory: https://gemini.google.com/share/3fdfb6c1bfdb
Architect: https://gemini.google.com/share/411d7640fbd4

---

**Question 1** The text explains that DynamoDB uses the **Partition Key** to determine the physical storage location of data via an internal hash function. It also states that DynamoDB scales by "automatic sharding."

Imagine you are building a logging application where millions of users generate event logs. You decide to use the **Timestamp** (e.g., `2023-10-27T10:00:00`) as the **Partition Key** because you often want to query logs by time.

**Why is this a terrible architectural decision that will likely cause "Hot Partitions" (throttling), even if you provision a huge amount of capacity?**

---

**Question 2** Let's fix the architecture from Question 1.

You decide to change the schema to use a **Composite Primary Key**:

- **Partition Key:** `UserID` (e.g., "User_123")
- **Sort Key:** `Timestamp` (e.g., "2023-10-27T10:00:00")

**1. How does this specific combination fix the "Hot Partition" writing problem we just discussed?** 
**2. How does this combination still allow you to efficiently answer the question: "Show me all logs for User_123 from yesterday?"**


---

**Question 3** Now, let's look at **Secondary Indexes**.

You have your running table:

- **PK:** `UserID`
- **SK:** `Timestamp`
- **Attributes:** `Status` (e.g., "INFO", "ERROR"), `Message`.

The Support Team suddenly demands a new feature: **"We need a dashboard showing ALL 'ERROR' logs that occurred in the last hour, across ALL users."**

You consider creating an index. The text says:
- **Local Secondary Index (LSI):** Uses the **same** partition key as the base table.
- **Global Secondary Index (GSI):** Can have a **different** partition key.

**Why is a Local Secondary Index (LSI) structurally incapable of solving this problem efficiently, forcing you to use a Global Secondary Index (GSI)?**