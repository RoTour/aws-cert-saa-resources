#AWS-SAA
Theory: https://gemini.google.com/share/aa8d0abfeae6
Architect: https://gemini.google.com/share/8794c1427ff3

---

### Critical Thinking Question 1

The text highlights that Secondary ENIs can be detached and moved to a different instance, and crucially, they carry their **Private IP**, **MAC address**, and **Elastic IP** (if attached) with them.

Most AWS users know you can easily remap a Public IP (Elastic IP) to a new server if the old one breaks.

**Why is the ability to preserve the _Private IP_ and _MAC address_ by moving the ENI so critical? Describe a scenario where remapping the Public IP alone would NOT save you.**

---

### Critical Thinking Question 2

The text states: _"The primary ENI (eth0) is permanently linked to its instance... it cannot be detached."_

This seems like a rigid constraint. You just explained why moving an ENI is great for recovery.

**If the Primary ENI is stuck on the instance, how do we architect a High Availability solution for a single-instance application (like a legacy SQL server) that relies on a specific IP address, given that the instance might die and take the Primary ENI down with it?**

---

