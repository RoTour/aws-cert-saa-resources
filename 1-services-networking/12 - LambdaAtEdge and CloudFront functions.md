#AWS-SAA
Theory: https://gemini.google.com/share/3a949f701a67
Architect: https://gemini.google.com/share/2deb6b605d35

---

### Critical Thinking Question #1

Let's focus on **Lambda@Edge** and the specific event triggers (`Viewer Request`, `Origin Request`, `Origin Response`, `Viewer Response`).

**Scenario:** You are tasked with building a feature that **dynamically resizes images** (e.g., resizing a 4K image down to a thumbnail) based on the user's device type. This is a CPU-intensive operation.

**The Question:** From an architectural perspective, why would it be a significant mistake to attach this heavy image-processing function to the **Viewer Request** or **Viewer Response** triggers?

Conversely, why is the **Origin Response** trigger typically the correct place for this, and how does it interact with the CloudFront Cache to save you money?

---

### Critical Thinking Question #2

Now, let's look at the "Trap" in this design.

Imagine this sequence of events based on your correct "Origin Response" design:

1. **User A (iPhone)** requests `banner.jpg`.
2. CloudFront has a cache miss, goes to Origin.
3. Your Lambda@Edge sees "iPhone", resizes the image to a tiny **300px** version.
4. CloudFront **caches** this 300px version as `banner.jpg`.
5. **User B (4K Desktop)** requests `banner.jpg`.

**The Problem:** CloudFront looks in the cache, sees `banner.jpg` is already there, and immediately serves the tiny **300px** image to the Desktop user. The Desktop user sees a blurry mess.

**As a Solutions Architect, how do you configure CloudFront to prevent this collision?**

---

**Critical Thinking Question #3**

Now, there is a dangerous side effect to this power.

If you simply check a box to include the **entire `User-Agent` header** in your Cache Key, you might destroy your cache performance.

Consider that `User-Agent` strings are very messy (e.g., "Mozilla/5.0 (iPhone; CPU iPhone OS 14_0 like Mac OS X) AppleWebKit/605.1.15..."). A minor browser update changes the string.

**If you include the raw `User-Agent` header in your Cache Key, what happens to your "Cache Hit Ratio," and why is that bad for your origin server?**

---

**Critical Thinking Question #4**

We need a standardized header (e.g., `Device-Type`) to use as our **Cache Key**.

**Which compute service (CloudFront Functions or Lambda@Edge) should you use to create this header, and on which trigger event (Viewer Request or Origin Request) must it run to ensure the cache works correctly?**

_Think about the order of operations: Request $\rightarrow$ ??? $\rightarrow$ Cache Check $\rightarrow$ ..._