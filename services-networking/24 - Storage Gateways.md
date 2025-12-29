#AWS-SAA
Theory: https://gemini.google.com/share/3859e3eb87d2
Architect: https://gemini.google.com/share/efe559ccc670

---

### Question 1: The "Latency Roulette"

The text highlights that **Volume Gateway - Cached Mode** is often preferred because it allows you to have "virtually unlimited" storage in the cloud while only keeping a small "cache" of frequently used data on your local hardware. This saves a lot of money on buying physical hard drives.

However, imagine you are the architect for a hospital. Doctors need to retrieve patient X-rays. While recent X-rays are accessed often, doctors frequently and unpredictably need to open X-rays from 10 years ago (Cold Data) during emergencies.

**Why might "Cached Mode" be risky or unsuitable for this specific hospital workflow? What happens technically when a doctor clicks on that 10-year-old file?**

---

### Question 2: The "File" vs. "Block" confusion

The text distinguishes between **File Gateway** (NFS/SMB) and **Volume Gateway** (iSCSI).

Imagine you have a legacy application running on an old Windows Server. This application was written in 2005 and is hard-coded to write logs to a `Z:` drive (a local disk drive letter).

**Which Gateway type MUST you use for this specific application, and why can't you use the other one?**

---

### Question 3: The "Migration" Trick

The text mentions that **Volume Gateway** stores data as **EBS Snapshots** in AWS.

Imagine you are migrating a database from your on-premise data center to run purely on EC2 in the cloud (a "Lift and Shift"). You install a Volume Gateway (Stored Mode) on-premise, copy your database data to it, and wait for the snapshot to upload to AWS.

**Once the data is in AWS as a snapshot, what is the final step to make that data available to your new EC2 instance running the database?**