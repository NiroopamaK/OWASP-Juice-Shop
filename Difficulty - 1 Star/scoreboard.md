## OWASP Juice Shop – Scoreboard Challenge

To solve the Scoreboard challenge in OWASP Juice Shop, basic client-side inspection techniques were used. The browser’s Developer Tools (e.g., Chrome DevTools) were opened, and the application’s source files were explored, focusing on the `main.ts` file, which contains the frontend logic.

While reviewing the code, a search for hidden routes revealed a path leading to the scoreboard page. By directly entering this route into the browser URL, the hidden scoreboard was accessed, successfully completing the challenge.

---

## Steps Taken to Solve the Challenge

1. **Open Developer Tools**  
  Accessed Chrome DevTools to inspect the application.

<img width="1193" height="841" alt="image" src="https://github.com/user-attachments/assets/5f5fe94b-d782-4307-ad3d-d17186a61b75" />

3. **Inspect Source Files**  
  Navigated through frontend files, particularly `main.ts`.

4. **Search for Hidden Routes**  
  Looked for references to routes that are not visible in the UI.

5. **Access the Route**  
  Entered the discovered path directly into the browser URL to access the scoreboard.

<img width="1196" height="466" alt="image" src="https://github.com/user-attachments/assets/12a9bf22-2a04-4718-b09e-cc057f9ae3f4" />

---

## Tools Used

- Browser Developer Tools (e.g., Chrome DevTools)  
- Source code inspection (frontend TypeScript files)  

---

## Key Learning Outcomes

- **Security through obscurity is not effective**  
  Simply hiding sensitive routes in frontend code does not prevent users from discovering them.

- **Client-side code is fully visible to users**  
  Any logic, routes, or secrets exposed in frontend files can be inspected and exploited.

- **Proper access control is essential**  
  Sensitive functionality (such as admin or scoreboard pages) should always be protected by server-side authentication and authorization checks.
