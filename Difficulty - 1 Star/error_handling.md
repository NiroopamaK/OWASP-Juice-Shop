## OWASP Juice Shop – Error Handling Challenge

In the Error Handling challenge of OWASP Juice Shop, the objective was to provoke an error that exposes backend details due to improper or overly verbose error handling. This challenge highlights how misconfigured error responses can leak sensitive system information. Web applications should handle errors in a controlled and generic manner. However, improperly configured servers may return verbose error messages that reveal internal implementation details such as frameworks, versions, or file paths. These details can be useful for attackers when identifying potential vulnerabilities.

<img width="1927" height="79" alt="image" src="https://github.com/user-attachments/assets/1fbaa5d1-9661-40f1-bacf-1f7c8d7dd7fe" />

<img width="1933" height="922" alt="image" src="https://github.com/user-attachments/assets/f5e820ca-1d79-4b51-8e5c-7dc256cdb430" />

---

## Steps Taken to Solve the Challenge

- **Experiment with URL Paths**  
  Attempted to access non-existent or restricted endpoints on the application to trigger error responses.

- **Provoke Specific Errors**  
  Tried requesting unsupported file types or directories to force the server into returning an error.

- **Analyze Error Messages**  
  Observed the server’s response and identified that it returned a detailed error message instead of a generic one.

---

## Solution Explanation

By accessing an invalid or restricted URL, the server returned a **403 error** along with a verbose message. The response revealed that the backend is running **Express.js version 4.17.1**. This information disclosure is significant because it exposes the underlying technology stack and version, which could allow attackers to research and exploit known vulnerabilities associated with that specific version.

---

## Tools Used

- Web browser  
- Knowledge of web server behavior and error handling  

---

## What This Teaches About Security

- **Avoid verbose error messages**  
  Detailed errors can leak sensitive backend information.

- **Information disclosure risk**  
  Revealing frameworks and versions helps attackers target known vulnerabilities.

- **Proper error handling**  
  Applications should return generic error messages to users while logging detailed errors securely on the server side.
