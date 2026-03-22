## OWASP Juice Shop – Repetitive Registration Challenge

In the Repetitive Registration challenge of OWASP Juice Shop, the objective was to exploit weaknesses in the registration process.

While testing the registration form, an initial attempt was made using matching values for the password and confirm password fields, which worked as expected. Further experimentation involved changing the password input and observing how the application handled validation.

It was discovered that the application did not consistently enforce password confirmation checks. By entering mismatching values in the password and repeat password fields, it was still possible to successfully register an account. This indicated a flaw in the validation logic, where the backend failed to properly verify that both fields matched.

---

## Steps Taken to Solve the Challenge

1. **Test Normal Registration**  
  Registered using matching password and confirm password values.

2. **Manipulate Input Fields**  
  Entered different values in the password and repeat password fields.

<img width="1191" height="711" alt="image" src="https://github.com/user-attachments/assets/2eaceb33-1073-4309-b0b5-3f4418833454" />

4. **Observe Application Behavior**  
  Noticed that the account was still created despite mismatched inputs.

---

## Tools Used

- Web browser (manual testing)  
- Chrome Developer Tools (optional, for observing requests)  

---

## What This Teaches About Security

- **Broken input validation**  
  Critical fields like password confirmation must always be validated server-side.

- **Inconsistent validation logic**  
  Even if the frontend enforces rules, backend inconsistencies can lead to vulnerabilities.

- **Business logic flaws**  
  Small validation oversights can allow unintended behavior, such as account creation with invalid data.
