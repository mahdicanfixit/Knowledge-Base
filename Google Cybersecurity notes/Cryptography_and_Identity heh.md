# Cryptography and Identity Access Management (IAM)

## 1. Asset Security
**Asset Classification:** Labeling assets based on sensitivity.
1.  **Public:** No restrictions.
2.  **Internal-Only:** Shared within the org, but not outside.
3.  **Confidential:** Limited to specific project teams (Need-to-Know).
4.  **Restricted:** Highly sensitive; strictest protection.

**Data States:**
* **At Rest:** Stored on a hard drive/server.
* **In Transit:** Moving across the network (e.g., email).
* **In Use:** Currently being processed by RAM/CPU.

---

## 2. Cryptography
The science of securing communication.

### Encryption Types


[Image of Symmetric vs Asymmetric encryption diagram]

* **Symmetric Encryption:** Uses **one shared key** to lock and unlock. Fast, but risky to share the key.
* **Asymmetric Encryption (PKI):** Uses a **Key Pair**.
    * **Public Key:** Everyone has it. Used to *encrypt* (Lock the box).
    * **Private Key:** Only you have it. Used to *decrypt* (Unlock the box).
* **Hashing:** One-way transformation (e.g., turning a password into `a3f9...`). Used to verify **Integrity**.

### PKI (Public Key Infrastructure)
A framework that manages digital keys and certificates to secure data exchange (like HTTPS).

---

## 3. Identity & Access Management (IAM)
**The AAA Framework:**
1.  **Authentication:** Verifying who you are.
2.  **Authorization:** Deciding what you can access.
3.  **Accounting:** Tracking what you did (Logs).

### Factors of Authentication
* **Something you Know:** Password, Security Question.
* **Something you Have:** Token, Smartphone (for OTP).
* **Something you Are:** Biometrics (Fingerprint, Face ID).

### Authentication Technologies
* **MFA (Multi-Factor Authentication):** Using 2+ factors (e.g., Password + Fingerprint).
* **SSO (Single Sign-On):** One login gives access to multiple apps.
* **OAuth:** An open standard that lets apps share access tokens (e.g., "Log in with Google").
    * **API Token:** Encrypted code identifying a user.
    * **Session ID:** Validates a user's active connection.
    * **Session Hijacking:** Attackers stealing a valid Session ID to impersonate a user.

---
*Back to [[Cybersecurity_Knowledge_Base]]*