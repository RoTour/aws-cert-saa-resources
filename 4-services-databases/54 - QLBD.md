#AWS-SAA
Theory: https://gemini.google.com/share/5bdb7e7c707a
Architect: https://gemini.google.com/share/af98c62d5024

---
### Question 1
   
   The text mentions that traditional databases _do_ have transaction logs (often used for disaster recovery) that record changes.
   
   **If a standard SQL database already has a log of every transaction, why is it fundamentally insufficient for a ledger application compared to QLDB's "append-only journal"?**
   
   Explain the specific architectural difference in how these two systems handle the concept of "history" and "trust."

---
### Question 2
   
   The text mentions that QLDB is "centralized" and owned by a trusted authority, yet it uses cryptographic concepts often found in Blockchain (like SHA-256 hashing and immutability).
   
   **Why would a company choose QLDB over a decentralized Blockchain (like Hyperledger Fabric or Ethereum) for a supply chain application?**
   
   Think about the trade-offs between "trust" and "performance/complexity."

---
### Question 3

The text explains that QLDB maintains a **Dual Table Structure**: a Current Table (C table) and a History Table (H table).

**Since the Journal already stores _every_ single transaction forever, why does QLDB bother maintaining a separate "Current Table" (C table)?**

Why not just calculate the current state by reading the Journal from the beginning whenever we need data?

---

### Question 4

The text mentions that QLDB uses **PartiQL** and a **document-oriented data model (Amazon Ion)** rather than a strict relational table schema.

**Why is a flexible _document_ model (like JSON/Ion) often better suited for a long-term ledger (like the "Car Lifecycle" example) compared to a rigid relational table structure?**

Think about how the information we track about a car might change over a 20-year period (e.g., a car made in 1990 vs. a car made in 2025).