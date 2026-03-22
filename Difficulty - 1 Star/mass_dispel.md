## OWASP Juice Shop – Mass Dispel Challenge

In the Mass Dispel challenge of OWASP Juice Shop, the objective was to close multiple “Challenge solved” notifications in a single action. This challenge focuses on efficiently navigating and utilizing application features rather than exploiting a security vulnerability. Upon completing several challenges in the Juice Shop interface, multiple “Challenge solved” notifications appeared. The documentation indicated that it was possible to close all visible notifications simultaneously using a specific key combination.

While holding the **Shift key**, clicking the close button on one notification resulted in all visible notifications being closed at once.

<img width="1593" height="944" alt="image" src="https://github.com/user-attachments/assets/78f6e773-d354-45ea-bb1c-0ce1a11a1e6c" />

---

## Solution Explanation

The challenge was solved by using a documented interface feature. Holding the **Shift key** while closing a notification triggers the application to close all active notifications, demonstrating how understanding application features can improve efficiency.

---

## Tools Used

- Web browser  
- OWASP Juice Shop Companion Guide (Documentation)  

---

## What This Teaches About Security

- **Awareness of application features**  
  Not all challenges are vulnerabilities; some require efficient use of UI functionality.

- **Documentation is valuable**  
  Referring to official guides can reveal hidden or less obvious features.

- **Efficiency in interaction**  
  Understanding shortcuts or key combinations can streamline workflows in web applications.
