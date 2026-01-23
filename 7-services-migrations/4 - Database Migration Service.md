#AWS-SAA
Theory: https://gemini.google.com/share/253c43b9ff22
Architect: https://gemini.google.com/share/f117eada0a46

---

**Question 1:** The lesson describes two distinct tools: **AWS DMS** (Database Migration Service) and the **AWS SCT** (Schema Conversion Tool).

Why does AWS separate these into two different tools? specifically, why can't the DMS service simply handle the schema conversion automatically "on the fly" while it is transferring the data?

---

**Question 2**

The lesson mentions the **Replication Instance**, which you have to provision (meaning you select a server size, like an EC2 instance).

If DMS is just moving data from Point A (Source) to Point B (Target), why does this "middleman" server need significant **Memory (RAM)** and **CPU**?

Why can't it just be a simple network tunnel that blindly passes packets from one side to the other?

_(Hint: Think about what happens if the Source is sending data faster than the Target can write it, or if the data formats are slightly different.)_

---

**Question 3**

We’ve talked about **CDC** (Change Data Capture), where DMS captures ongoing changes.

How does DMS actually _know_ that a row has changed in the source database?

DMS does **not** constantly run `SELECT * FROM Table` to check for changes (that would crash your production server). So, what specific mechanism or feature _on the source database_ does DMS rely on to capture these updates in real-time?

_(Hint: Every database uses this feature to ensure it can recover data after a crash.)_
