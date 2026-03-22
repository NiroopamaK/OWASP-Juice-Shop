## OWASP Juice Shop – Missing Encoding Challenge

In the Missing Encoding challenge of OWASP Juice Shop, the goal was to retrieve a specific image from the application that failed to load due to improper URL encoding. This challenge highlights how browsers handle URLs and the importance of encoding special characters correctly.

While exploring the photo wall of the application, one image failed to load. Using browser Developer Tools to inspect the element, it was found that the `src` attribute of the image contained special characters, such as emojis, that were not URL encoded. This caused the browser to fail when attempting to fetch the image from the server.

<img width="1196" height="709" alt="image" src="https://github.com/user-attachments/assets/3da5cc95-440f-452b-a4c1-7f252955a46a" />

---

## Steps Taken to Solve the Challenge

1. **Identify the Issue**  
  Observed the broken image and inspected its `src` attribute to find special characters (e.g., emojis) causing the loading failure.

2. **Understand the Problem**  
  Recognized that browsers require proper URL encoding for special characters; otherwise, the URL is interpreted incorrectly, preventing the resource from being fetched.

3. **Use URL Encoding Tool**  
  Used an online URL encoding tool to encode the image URL, transforming special characters into a browser-compatible format. The encoded URL obtained was:  
  `assets%2Fpublic%2Fimages%2Fuploads%2F%F0%9F%98%BC-%23zatschi-%23whoneedsfourlegs-1572600969477.jpg`

4. **Replace the URL**  
  Copied the encoded URL and replaced the original `src` attribute in the image tag using browser Developer Tools.

5. **Reload and Verify**  
  Refreshed the page or reloaded the image to confirm it displayed correctly.

---

## Solution Explanation

The challenge was solved by properly encoding the URL so that the browser could correctly interpret and fetch the image. Special characters, like emojis, must always be URL encoded to ensure web resources are accessible.

---

## Tools Used

- Browser Developer Tools (Elements tab)  
- Online URL Encoding Tool  

---

## What This Teaches About Security

- **Proper encoding matters**  
  URLs with special characters must be correctly encoded to prevent resource access issues.

- **Input validation and encoding are important**  
  Applications should ensure resources are accessible and safely encoded.

- **Understanding web standards**  
  Awareness of how browsers parse URLs can prevent subtle functional and security issues.
