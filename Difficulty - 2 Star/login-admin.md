# OWASP Juice Shop – Login Admin Challenge

## Initial Analysis
The objective of this challenge is to gain access to the administration section of the application, which is normally restricted to users with admin privileges. During exploration, it was noted that the login page accepts an email and password combination and that the application uses JSON Web Tokens (JWT) for session management.

Inspecting the frontend and network traffic revealed that the JWT contains user role information, such as `"role": "customer"`. The application relies on this token for access control in the client interface, suggesting a potential weakness if the token can be manipulated.

![success](https://github.com/user-attachments/assets/f793f75a-7c6a-4708-90ce-01a443a80428)

---

## Tools Used

- **Web Browser (Firefox/Chromium):** To interact with the login page and administration section.  
- **Browser Developer Tools:** To inspect JWT tokens stored in Local Storage or cookies and to modify payloads.  
- **JWT Decoder / Editor (Online or via DevTools):** To view and modify the token payload.  

---

## Steps Taken to Solve the Challenge

### 1. Navigate to the Login Page
- Opened Juice Shop login page
- Prepared to examine a normal user login session

### 2. Inspect the JWT
- Logged in with a regular account
- Opened Developer Tools → Application → Local Storage
- Retrieved the JWT token and decoded it
- Observed that the payload contained a `"role"` field with value `"customer"`

### 3. Modify the JWT
- Edited the token payload to change `"role": "customer"` to `"role": "admin"`

### 4. Replace Token in Local Storage
- Overwrote the existing token in Local Storage with the modified token

### 5. Access Administration Section
- Navigated to `#/administration` in the browser
- With the modified token, the application displayed the admin panel
- Challenge marked as completed

<img width="2875" height="1703" alt="image" src="https://github.com/user-attachments/assets/1037a11a-d8c3-4454-8ed4-fb714e63fcd9" />

---

## Solution Explanation

The vulnerability exploited in this challenge demonstrates **Broken Access Control**:

- The application relies on the **client-side JWT** for determining user roles without enforcing server-side authorization checks.
- By manipulating the JWT to change the role from `"customer"` to `"admin"`, the frontend granted administrative access.
- No backend validation of the token’s role was performed before granting access to the admin section.

This highlights a key security principle:

- **Never trust the client for role-based access control.**  
- Server-side checks are required for all sensitive or privileged operations.

---

## Key Takeaways

- Access control must always be enforced on the server, not just on the client.  
- JWTs stored in the browser can be modified by the user if the server does not validate them properly.  
- This challenge illustrates a real-world risk of **privilege escalation** via token manipulation.
