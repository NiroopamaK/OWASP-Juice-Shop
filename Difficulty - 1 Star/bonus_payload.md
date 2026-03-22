# OWASP Juice Shop – Bonus Payload Challenge

In the Bonus Payload challenge of OWASP Juice Shop, the objective was to extend the previous DOM XSS exploit by injecting a more complex payload. This involved embedding a fully functional iframe containing a SoundCloud player into the application’s DOM. Following the earlier DOM XSS vulnerability, the application’s search functionality (q parameter) was already identified as an injection point. Since user input is directly reflected into the DOM without proper sanitization, it is possible to inject not only simple scripts but also complex HTML elements such as iframes.

<img width="2141" height="145" alt="image" src="https://github.com/user-attachments/assets/23600d44-bc4c-4435-be12-aa8cd0a875ca" />

<img width="1310" height="780" alt="image" src="https://github.com/user-attachments/assets/323dbd33-bbba-4783-adbe-04381c463662" />

---

## Steps taken to solve this challenge 
1. Understand the Payload
The provided payload consisted of an iframe embedding a SoundCloud music player. This demonstrated that arbitrary third-party content could be injected into the application.

2. Craft and Encode the Payload
URL-encoded the iframe payload to ensure it would be correctly interpreted when passed as a query parameter.

 Example injected URL:
http://127.0.0.1:3000/#/search?q=%3Ciframe%20width%3D%22100%25%22%20height%3D%22166%22%20scrolling%3D%22no%22%20frameborder%3D%22no%22%20allow%3D%22autoplay%22%20src%3D%22https:%2F%2Fw.soundcloud.com%2Fplayer%2F%3Furl%3Dhttps%253A%2F%2Fapi.soundcloud.com%2Ftracks%2F771984076%26color%3D%2523ff5500%26auto_play%3Dtrue%26hide_related%3Dfalse%26show_comments%3Dtrue%26show_user%3Dtrue%26show_reposts%3Dfalse%26show_teaser%3Dtrue%22%3E%3C%2Fiframe%3E

3. Execute the Attack
Navigated to the crafted URL, which caused the application to render the iframe directly in the DOM.

---
## Solution Explanation
The challenge was solved by successfully injecting a complex iframe payload via a DOM-based XSS vulnerability. The application rendered the iframe without sanitization, allowing external content (in this case, a SoundCloud player) to be embedded.
This demonstrates that XSS is not limited to simple alert pop-ups, attackers can inject full-featured external content, potentially leading to phishing, malicious redirects, or content injection attacks.

---
## Tools used
- Web browser

---
## What this teaches about security
- XSS can inject complex content: Attackers can embed full applications or third-party services, not just scripts.
- DOM-based vulnerabilities are dangerous: Unsanitized input directly inserted into the DOM creates serious risks.
- Content injection risks: Embedded external content can be used for phishing, tracking, or malicious interactions.
