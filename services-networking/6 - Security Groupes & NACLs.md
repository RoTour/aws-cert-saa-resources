Theory: https://gemini.google.com/share/cc820c296a31
Architect: https://gemini.google.com/share/9de271d203a2

---

**Critical Thinking Question 1**

Security Groups are often the primary firewall we use because they are stateful and easy to manage. However, the text highlights that they operate on an **"Allow-only"** basis.

Imagine you are a Solution Architect monitoring traffic logs. You discover that a specific malicious IP address (`198.51.100.55`) is launching a denial-of-service attack against your application.

1. Why is it **impossible** to use a Security Group to explicitly stop this specific attacker while keeping the application open to the rest of the world?
    
2. How would you use a **Network ACL** to solve this problem, and why does the **Rule Number** you choose for this configuration matter significantly?
