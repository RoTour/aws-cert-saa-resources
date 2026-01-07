#AWS-SAA
Theory: https://gemini.google.com/share/ebceb3f55f9d
Architect: https://gemini.google.com/share/95855acc803e

---

### Critical Thinking Question #1

The lesson states that OpenSearch excels at handling "semi-structured data" and "full-text search," while relational databases (like RDS/PostgreSQL) excel at structured data.

Imagine you are building a **Product Catalog** for a massive online store with millions of items. The product data (ID, price, stock count) is currently stored in **Amazon RDS** (a relational database).

Your Product Manager asks you to implement a search bar on the website where users can type vague queries like _"red running shoes cheap"_ or _"comfy summer wear"_.

**Question:** Why would an architect recommend replicating this data into **OpenSearch** specifically for this feature, rather than just running SQL queries (like `SELECT * FROM products WHERE description LIKE '%red running shoes%'`) directly against the **RDS** database?

---

### Critical Thinking Question #2

The text mentions that **OpenSearch Ingestion** is a "fully managed, serverless data collector" that can "handle data transformation and cleaning" before delivering data to the cluster, removing the need for third-party tools like Logstash.

**Scenario:** Your company has 50 different microservices built by different teams. You discover that many of these services are accidentally logging sensitive User Emails in plain text. You need to fix this immediately to meet compliance rules (mask emails to `u***@example.com`).

**Question:** You have two architectural choices:

1. **Source Fix:** Force all 50 teams to update their application code to mask the data before logging it, then redeploy their services.
    
2. **Pipeline Fix:** Configure the **OpenSearch Ingestion** pipeline to detect email patterns and mask them in transit.
    

As a Solution Architect, why is **Option 2 (The Pipeline Fix)** generally considered the superior approach in this specific situation?

---

### Critical Thinking Question #3

The resource mentions that OpenSearch supports "up to three petabytes of attached storage." However, storing 3PB of data on high-performance SSDs (Hot storage) is astronomically expensive.

OpenSearch (like Elasticsearch) solves this using a **Tiered Storage** architecture (Hot, UltraWarm, Cold).

**Scenario:** You are archiving 3 years of system logs for a bank.
- **Week 1 logs:** Accessed every minute by developers debugging live issues.
- **Month 1-3 logs:** Accessed occasionally (once a week) for trend analysis.
- **Year 1-3 logs:** Almost never accessed, but must be kept for legal compliance.

**Question:** How should you organize these data stages across OpenSearch storage tiers to optimize for **Cost vs. Performance**? Explain _why_ you would move the Year 1-3 logs to "Cold" storage instead of just deleting them or keeping them on "Hot" nodes.