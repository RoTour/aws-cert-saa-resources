#AWS-SAA 
Theory: https://gemini.google.com/share/3ff6122ddb48
Architect: https://gemini.google.com/share/957ccb6849a2

---

**Context:** Standard VPC peering is **non-transitive**. This means that if VPC A is peered with VPC B, and VPC B is peered with VPC C, VPC A cannot send traffic to VPC C through VPC B.

**Question:** If you are a network architect managing an environment that scales from 3 to 50 VPCs, and you require full connectivity between all of them:

1. What specific network **topology** (or shape) does this "non-transitive" rule force you to build if you are using only VPC Peering?
    
2. From an operational standpoint, why is that specific topology considered unsustainable compared to the **hub-and-spoke** model used by a Transit Gateway?

---

**Context:** The text mentions a specific configuration requirement: _"designate one subnet from each availability zone... ensures that the Transit Gateway has sufficient network interfaces."_

**Question:** Imagine you have a critical production VPC spanning **two** Availability Zones (AZ-A and AZ-B). To save IP addresses, you decide to create the Transit Gateway attachment (the network interface) **only in AZ-A**.

From a **High Availability (HA)** perspective, why is this a dangerous architectural decision? Specifically, describe the impact on the resources running in **AZ-B** if a failure occurs in **AZ-A**.

---

**Context:** Simply "attaching" a VPC to a Transit Gateway does not automatically route traffic to it. The attachment just builds the bridge; it doesn't force cars to drive over it.

**Question:** You have successfully attached **VPC A** (10.0.0.0/16) and **VPC B** (10.1.0.0/16) to the Transit Gateway. However, an EC2 instance in VPC A still cannot reach an instance in VPC B.

What specific component **within VPC A** must you modify to tell the network: _"If you are looking for 10.1.0.0/16 (VPC B), go through the Transit Gateway"_?

---

**Context:** You have updated the route table in **VPC A**. The packet successfully leaves VPC A, travels through the Transit Gateway, and reaches the EC2 instance in **VPC B**. The instance in VPC B accepts the traffic.

**Question:** However, the connection still fails (e.g., a ping times out). The instance in VPC A never receives a response.

Why? What specific configuration is missing in **VPC B** that prevents the reply from getting back?