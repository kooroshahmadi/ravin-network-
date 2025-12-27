---
tags:
  - security/iam
  - authorization
created: 2025-12-28
check: verified
---

# Authorization Models

Once you are logged in (Authenticated), what can you touch?

### 1. DAC (Discretionary Access Control)
*   **Concept:** The **Owner** decides.
*   **Example:** You create a file in Windows. You right-click -> Properties -> Share -> Add Bob.
*   **Pros/Cons:** Flexible, but insecure (users make mistakes).

### 2. RBAC (Role-Based Access Control)
*   **Concept:** The **Job Title** decides.
*   **Example:** "Nurses" can see patient records. "Janitors" cannot. You put Bob in the "Nurse" group.
*   **Pros/Cons:** Easy to manage in large companies.

### 3. ABAC (Attribute-Based Access Control)
*   **Concept:** The **Context** decides ("The Smart Model").
*   **Example:** "Allow access IF User=Nurse AND Time=9am-5pm AND Location=Hospital_Wi-Fi."
*   **Pros/Cons:** Most secure/flexible, but hardest to set up.

### 4. MAC (Mandatory Access Control)
*   **Concept:** The **Government** decides. Labels (Top Secret / Classified). Users cannot change permissions.