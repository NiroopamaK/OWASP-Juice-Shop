## OWASP Juice Shop – Allowlist Bypass Challenge

Upon inspecting the challenge, it was observed that the application generates QR codes for cryptocurrency transactions. By examining the frontend JavaScript (`main.js`), specific cryptocurrency addresses were found to be hard-coded in the code. A redirect function pointed to these addresses based on user selection, meaning the allowlist of valid addresses was embedded in the client-side code.

---

## Steps Taken to Solve the Challenge

1. **URL Manipulation**  
  Modified the redirect URL parameter to point to a different cryptocurrency address that was still on the allowlist.

<img width="1197" height="706" alt="image" src="https://github.com/user-attachments/assets/0198851a-59a5-4d54-9a2e-aac6d20477eb" />

3. **Access the Modified URL**  
  Opened the following in the browser:  
```
http://192.168.123.111:3000/redirect?to=https://www.blockchain.com/explorer/addresses/btc/1AbKfgvw9psQ41NbLi8kufDQTezwG8DRZm

```

<img width="1193" height="714" alt="image" src="https://github.com/user-attachments/assets/4fc3e408-2d64-4305-b780-386303e579e9" />


5. **Observe the Result**  
  The backend accepted the input, successfully completing the challenge.

---

## Solution Explanation

The challenge was solved by exploiting an outdated allowlist in the frontend. Even though the frontend limited selectable options, the backend still accepted a previously allowed address.

This demonstrates how stale or incomplete allowlists can be bypassed when proper validation is not enforced server-side.

---

## Tools Used

- Browser Developer Tools (Elements, Sources)  
- Manual URL manipulation  

---

## What This Teaches About Security

- **Frontend allowlists can be bypassed**  
  Users can manipulate URLs or inputs to access restricted functionality.

- **Backend validation is essential**  
  Security must be enforced server-side, not just through client-side checks.

- **Outdated security controls are risky**  
  Hard-coded lists or legacy rules can create vulnerabilities if not maintained.
