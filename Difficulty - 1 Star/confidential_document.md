# OWASP Juice Shop – Confidential Document Challenge

In this challenge of OWASP Juice Shop, the objective was to access and retrieve a confidential document (acquisition.md) from an exposed FTP directory. This highlights issues related to sensitive data exposure due to improper access control. The application exposes an FTP directory that is accessible via the browser. Such directories may contain sensitive files if not properly secured. Upon exploration, it was possible to view a list of files hosted on the server.

<img width="1830" height="73" alt="image" src="https://github.com/user-attachments/assets/8640e032-baac-445b-bb74-e9e3d746526d" />

<img width="1836" height="927" alt="image" src="https://github.com/user-attachments/assets/981a9605-7099-49b9-9f9f-f514ffc7d861" />

---

## Steps taken to solve this challenge 
1. Access the FTP Server
Navigated to the FTP directory at: http://192.168.123.111:3000/ftp

2. Identify the Target File
Located the file acquisition.md, which appeared to contain confidential business information based on its name.

3. Download the File Using curl
Used the command line to download the file directly:
```
 curl http://192.168.123.111:3000/ftp/acquisition.md -o acquisition.md
```
5. Review the File
Opened the downloaded file and confirmed it contained confidential information about planned company acquisitions.

---
## Solution Explanation
The challenge was solved by directly downloading a sensitive file from a publicly accessible FTP directory using curl. The file contained confidential business data, demonstrating a lack of proper access control and secure storage practices.

---
## Tools used
- Web browser
- Command Line (curl)

---
## What this teaches about security
- Sensitive data exposure: Confidential files should never be publicly accessible.
- Improper access control: Directories must be protected with authentication and authorization mechanisms.
- Directory enumeration risks: Attackers can easily discover and retrieve exposed files.

