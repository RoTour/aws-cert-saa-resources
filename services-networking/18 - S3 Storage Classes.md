#AWS-SAA
Theory: https://gemini.google.com/share/7adee6fae698
Architect: QUIZ_LINK

---

| **Storage Class**           | **Min. Duration** | **Min. Object Size** | **Retrieval Time** |
| --------------------------- | ----------------- | -------------------- | ------------------ |
| **S3 Standard**             | None              | None                 | Milliseconds       |
| **S3 Intelligent-Tiering**  | None*             | None*                | Milliseconds       |
| **S3 Standard-IA**          | 30 Days           | 128 KB               | Milliseconds       |
| **S3 One Zone-IA**          | 30 Days           | 128 KB               | Milliseconds       |
| **S3 Glacier Instant**      | 90 Days           | 128 KB               | Milliseconds       |
| **S3 Glacier Flexible**     | 90 Days           | 40 KB                | 1 min – 12 hours   |
| **S3 Glacier Deep Archive** | 180 Days          | 40 KB                | 12 – 48 hours      |

> **Note on Intelligent-Tiering:** While there is no minimum duration or size for _billing_ the storage itself, objects smaller than 128 KB are never moved to infrequent tiers and are always billed at the Frequent Access rate.


---

### **Question 1**

Imagine you are designing a storage solution for a medical imaging company. They produce thousands of high-resolution X-ray images daily.

- For the first **30 days**, these images are accessed constantly by doctors.
- After **30 days**, the images are rarely touched, but if an emergency surgery occurs, the doctor **must** be able to pull the image within seconds.    
- The company is extremely cost-conscious and wants to avoid paying for multi-AZ redundancy for these older images because they have a physical backup on-site.

**Based on these requirements, what specific S3 storage class strategy would you recommend for the images after the first 30 days, and why?**

---

### **Question 2 (Critical Thinking)**

Let's stick with the cost-optimization theme.

Suppose you have a massive dataset of 1-kilobyte log files (billions of them). These logs are accessed once a year for a compliance audit. You decide to move them all to **S3 Standard-IA** to save on storage costs.

**Based on the table we built and the mechanics of S3 billing, why might this "optimization" actually result in a much higher bill than keeping them in S3 Standard?**