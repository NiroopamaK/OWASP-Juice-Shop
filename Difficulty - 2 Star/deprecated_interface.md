# OWASP Juice Shop – Deprecated Interface Challenge

## Initial Analysis  
The objective of this challenge was to identify and exploit a deprecated interface within the application. During exploration of OWASP Juice Shop, the `/complain` page stood out as a potential target. This feature appeared outdated, especially since newer versions of the application promote a chatbot-based support system, suggesting that the complaint form may no longer be actively maintained.

Further inspection using browser Developer Tools revealed that the complaint form included a file upload functionality. Reviewing the `main.js` file showed that the uploader enforced client-side restrictions on file types, allowing only specific MIME types such as `application/pdf`, `application/zip`, and `text/xml`. This indicated a possible weakness, as client-side validation alone is insufficient for secure file handling.
<img width="2784" height="224" alt="image" src="https://github.com/user-attachments/assets/a3a2cc70-0fce-4a78-abf1-4ab2fa065b02" />

---

## Tools Used  

- **Web Browser (Firefox/Chromium):** To interact with the application and access the `/complain` interface  
- **Browser Developer Tools:** For inspecting JavaScript (`main.js`), modifying DOM elements, and bypassing client-side restrictions  
- **Kali Linux Terminal:** To create and manipulate files used in the attack (XML payload and renaming)  

---

## Steps Taken to Solve the Challenge  

### 1. Accessing the Deprecated Interface  
- Navigated to the `/complain` page within the application  
- Identified that it still allowed file uploads despite being deprecated  

### 2. Analyzing File Upload Restrictions  
- Inspected `main.js` via Developer Tools  
- Observed that file uploads were restricted based on MIME type and file extension on the client side  

### 3. Creating a Test XML File  
- Created a simple XML file

### 4. Attempting Direct Upload  
- Uploading the .xml file directly was blocked due to client-side validation

### 5. Bypassing Client-Side Validation 
- Used Developer Tools to remove the file input restriction [document.querySelector('input[type="file"]').accept = '*/*']
- This disabled the frontend file type filtering mechanism
![how to do](https://github.com/user-attachments/assets/613dd0f7-3c9f-43bc-b880-381a55e795a6)

### 6. Uploading the Malicious File 
- Uploaded the XML file successfully after bypassing restrictions
- Submitted the complaint form with the attached file

### 3. Creating a Test XML File  
- Created a simple XML file

---

## Solution Explanation 
The vulnerability exploited in this challenge stems from reliance on client-side validation within a deprecated interface. The /complain feature allowed file uploads but only enforced restrictions in the browser using JavaScript. By modifying the DOM and removing the accept attribute from the file input field, these restrictions were bypassed.

Since the backend did not properly validate the file type, the application accepted the uploaded XML file. This demonstrates a classic security flaw where:
- Client-side controls are trusted 
- Server-side validation is insufficient 

In real-world scenarios, such weaknesses could lead to more severe exploits, such as:
- XML External Entity (XXE) attacks
- Arbitrary file uploads
- Remote code execution (depending on server handling)

This challenge highlights the risks of leaving deprecated functionality exposed and failing to enforce server-side validation, both of which are common issues in real-world applications.
