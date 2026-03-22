# OWASP Juice Shop -  Bjoern’s Favorite Pet

## Challenge Overview
The **“Bjoern’s Favorite Pet”** challenge from OWASP Juice Shop focuses on exploiting weak account recovery mechanisms using publicly available information.
The objective is to identify the name of Bjoern’s favorite pet, which is used as the answer to a security question for account recovery.

![success message](https://github.com/user-attachments/assets/43b9f4e6-73a9-4a8c-9df5-3bc529df76b5)

---

## Tools Used

- Web Browser – Accessing the application and social media platforms  
- OSINT Techniques – Gathering publicly available information  
- Twitter 

---

## Methodology and Solution

### 1. Initial Enumeration

- Logged into the admin panel of the application  
- Viewed the list of registered users  
- Identified Bjoern’s account and retrieved his email: "bjoern@owasp.org"

![bjorn email](https://github.com/user-attachments/assets/78ce1e00-4def-40a4-8134-ce9cb7330ce0)

---

### 2. OSINT Investigation

- Used the email address to search for associated online profiles  
- Located Bjoern’s Twitter account  

On his profile:
- Found a post mentioning his cat  
- The cat’s name was revealed as: Zaya


---

### 3. Exploiting Password Recovery

- Navigated to the **“Forgot Password”** functionality  
- Entered Bjoern’s email address  
- Answered the security question
- Successfully reset the password  
- Logged into Bjoern’s account
  
![forget password](https://github.com/user-attachments/assets/9176d6e2-95bd-4b7a-917e-768c59fa6ca0)

---

## Solution Explanation

This challenge demonstrates how **Open Source Intelligence (OSINT)** can be used to bypass authentication mechanisms.

By combining:
- Sensitive data exposure (email from admin panel)  
- Public social media information  

an attacker can successfully compromise a user account.

The key weakness lies in relying on **knowledge-based authentication (security questions)** that can be easily answered using publicly available data.

---

## Conclusion

The challenge highlights how weak recovery mechanisms combined with OSINT can lead to full account compromise. It reinforces the importance of secure authentication design and careful handling of personal information.


