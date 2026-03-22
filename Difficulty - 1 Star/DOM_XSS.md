# OWASP Juice Shop – DOM XSS Challenge

In the DOM XSS challenge of OWASP Juice Shop, the objective was to perform a DOM-based Cross-Site Scripting (XSS) attack by injecting malicious JavaScript into the application’s Document Object Model (DOM). This challenge focuses on client-side vulnerabilities where user input is not properly sanitized before being rendered in the browser. The application includes a search functionality that reflects user input directly into the DOM. The query parameter (q) in the URL was identified as a potential injection point, as it dynamically updates page content without proper sanitization. This creates an opportunity for DOM-based XSS.

<img width="1840" height="99" alt="image" src="https://github.com/user-attachments/assets/e0f034f4-4551-4176-ae92-f380099cc09b" />

---

## Steps taken to solve this challenge 
1. Identify the Injection Point
Determined that the search feature (#/search?q=) directly interacts with the DOM and could be used to inject malicious input.

2. Craft the Payload
Created an XSS payload using an iframe element:
```
 <iframe src="javascript:alert(`xss`)">
```
This payload executes JavaScript through the iframe’s src attribute.

3. Encode and Inject the Payload
URL-encoded the payload to ensure proper transmission in the browser:
```
http://192.168.123.111:3000/#/search?q=%3Ciframe%20src=%22javascript:alert(%60xss%60)%22%3E
```

4. Execute the Attack
Navigated to the crafted URL, which caused the browser to interpret the injected payload and execute the JavaScript.
---
## Solution Explanation
The challenge was solved by injecting a malicious iframe payload into a URL parameter that directly modifies the DOM. Because the application failed to sanitize user input, the browser executed the injected JavaScript, resulting in a successful DOM-based XSS attack.

---
## Tools used
- Web browser

---
## What this teaches about security
- DOM-based XSS risks: Client-side rendering without sanitization can lead to script execution.
- Input sanitization is critical: All user input must be validated and sanitized before being inserted into the DOM.
- Avoid dangerous patterns: Using javascript: in attributes like src can introduce serious vulnerabilities.

