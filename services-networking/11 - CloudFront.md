#AWS-SAA
Theory: https://gemini.google.com/share/3298ab647234
Architect: https://gemini.google.com/share/7c037719606f

---

**Critical Thinking Question #1**

CloudFront is explicitly designed to reduce latency by serving content from Edge Locations closer to the user. However, functionally, CloudFront acts as an intermediary between the user and the Origin.

**Analyze a specific scenario where a user's request via CloudFront results in _higher_ latency than if they had connected directly to the Origin server.**

---

**Critical Thinking Question #2**

Let's stick with this idea of "Caching" versus "Delivery."

The text mentions that CloudFront accelerates **"dynamic content"** (like a personalized dashboard or a shopping cart).

**Here is the paradox:** Dynamic content changes for every single user. You cannot cache a shopping cart, because my cart is different from yours. If CloudFront caches it, I might see your items!

**If CloudFront cannot cache this dynamic content, how exactly does it "accelerate" the delivery of it?**

---

**Critical Thinking Question #3**

We have established that CloudFront is great for downloading things (GET requests). But modern applications are interactive.

**Consider a scenario where users are _uploading_ large files (PUT/POST requests) to your application, such as uploading a 1GB video file to an S3 bucket.**

Does CloudFront offer any benefit for **uploading** data, or is it strictly for downloading? If it does help, _how_ does the architecture facilitate faster uploads?
