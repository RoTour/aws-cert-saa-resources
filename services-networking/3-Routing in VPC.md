Theory: https://gemini.google.com/share/486ed5deaa94
Architect: https://gemini.google.com/share/eeb88f3328eb

---

**Question 1:** The text explains that when multiple routes match a packet's destination (for example, an overlapping `10.16.1.0/24` and `10.16.0.0/16`), the VPC router explicitly prioritizes the **Longest Prefix Match** (the most specific route).

Critically analyze why this prioritization logic is essential for network segmentation. Specifically, how does this rule allow a Solution Architect to implement "exception-based" routing—where a specific subset of traffic must be handled differently (e.g., sent to a firewall) than the rest of the broader network traffic?

---

**Critical Thinking Question 2**

The text mentions that every Route Table contains a **mandatory "local" route** for the VPC's main CIDR block (e.g., `10.0.0.0/16`), and implied is that this route **cannot be deleted or modified**.

**Question:** If you cannot delete the "local" route, you cannot use the Route Table to prevent Subnet A (Web Tier) from talking to Subnet B (Database Tier) if they are in the same VPC.

As an architect, since you cannot rely on _routing_ to block traffic between these internal subnets, **what specific security layer** must you rely on to enforce this segmentation? Explain why the router effectively "ignores" your desire to separate them.
