#AWS-SAA
Theory: https://gemini.google.com/share/b8d61ed44d13
Architect: https://gemini.google.com/share/64d2f92d1937

---

### Question 1

In the demo, you built a **State Machine** that calls the `detect_threat` Lambda, waits for the result, and _then_ calls either `threat_found` or `false_positive`.

A developer on your team asks: _"Why are we complicating this with Step Functions? Why don't we just write code inside the `detect_threat` Lambda to call the next Lambda function directly using the AWS SDK?"_

**What is the specific architectural risk of having Lambda functions call other Lambda functions directly (Lambda chaining), and how does Step Functions solve it?**

---

### Question 2

The text mentions that you can configure the **Input/Output payload** between states.

In the demo, the `detect_threat` function returns `{ "result": "THREAT" }`.

Imagine a more complex scenario:

1. **State 1 (Camera):** Captures metadata `{ "cam_id": "A1", "time": 1200 }`.
    
2. **State 2 (Detect):** Runs analysis and returns `{ "threat_level": "HIGH" }`.
    
3. **State 3 (Alert):** Needs **BOTH** the `cam_id` (from State 1) and the `threat_level` (from State 2) to send an email saying "Camera A1 detected HIGH threat."
    

**By default, State 2's output _replaces_ State 1's input. How does Step Functions allow State 3 to see data from State 1 if State 2 overwrites it?**

(Hint: It involves the "ResultPath" or how data is passed through the JSON state.)

---

### Question 3

Let's look at **Timeouts and Waiting**.

Standard AWS Lambda functions have a maximum execution timeout of **15 minutes**.

**Scenario:** You need a workflow where:

1. A user uploads a document.
2. A Manager receives an email to "Approve" or "Reject" it.
3. The Manager might take **3 days** to click the link in the email.
4. Once clicked, the workflow continues to "Process Payment."

**Why is Step Functions the _only_ serverless way to handle this 3-day wait, and how does it technologically achieve "waiting" without you paying for a running server?**