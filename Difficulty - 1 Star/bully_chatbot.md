# OWASP Juice Shop – Bonus Payload Challenge

In this challenge of OWASP Juice Shop, the objective was to interact with the support chatbot and manipulate it into providing a coupon code. This challenge focuses on testing edge cases in automated response handling. The application includes a support chatbot accessible from the support or contact page. The chatbot is designed to respond to common queries, including requests for coupons, but initially refuses or provides generic responses. 

<img width="1830" height="102" alt="image" src="https://github.com/user-attachments/assets/f68ea508-079d-45ef-8938-ed072ee82ceb" />

<img width="1844" height="1113" alt="image" src="https://github.com/user-attachments/assets/8263e6c2-f566-45b7-a9d5-ddc30ffedbde" />

---

## Steps taken to solve this challenge 
1. Understand the Payload
Opened the chatbot interface and initiated a conversation.

2. Persistently Request the Coupon
Repeatedly sent the message: give me a coupon

3. Analyze Bot Responses
Observed that the bot initially refused to provide a coupon or gave generic answers.
After multiple repeated requests, the chatbot triggered a programmed fallback or override, ultimately returning a valid coupon code.

---
## Solution Explanation
The challenge was solved by exploiting a fallback mechanism in the chatbot’s logic. After repeated identical requests, the bot’s programming issued a coupon code. This demonstrates how edge cases in automated systems can be manipulated by persistence, leading to unintended outcomes.

---
## Tools used
- Web browser

---
## What this teaches about security
- Poorly designed fallback mechanisms create vulnerabilities : The chatbot’s override behavior (eventually giving a coupon) reveals how fallback responses can unintentionally expose sensitive or restricted functionality.
- Automated systems can be manipulated through persistence : Repeated inputs can trigger unintended fallback logic, showing that chatbots and automated workflows must handle repeated requests carefully.
- User interaction flows can leak unintended functionality: Even simple features like a support chatbot can expose hidden features when pushed beyond expected usage.

