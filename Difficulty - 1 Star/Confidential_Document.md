In this challenge of OWASP Juice Shop, the objective was to access and retrieve a confidential document (acquisition.md) from an exposed FTP directory. This highlights issues related to sensitive data exposure due to improper access control.

Initial Analysis
The application exposes an FTP directory that is accessible via the browser. Such directories may contain sensitive files if not properly secured. Upon exploration, it was possible to view a list of files hosted on the server.

Steps Taken to Solve the Challenge
Access the FTP Server
 Navigated to the FTP directory at: http://192.168.123.111:3000/ftp
Identify the Target File
 Located the file acquisition.md, which appeared to contain confidential business information based on its name.
Download the File Using curl
 Used the command line to download the file directly:
 curl http://192.168.123.111:3000/ftp/acquisition.md -o acquisition.md


Review the File
Opened the downloaded file and confirmed it contained confidential information about planned company acquisitions.

Solution Explanation
The challenge was solved by directly downloading a sensitive file from a publicly accessible FTP directory using curl. The file contained confidential business data, demonstrating a lack of proper access control and secure storage practices.

Tools Used
Web browser
Command line (curl)

What This Teaches About Security

Sensitive data exposure: Confidential files should never be publicly accessible.
Improper access control: Directories must be protected with authentication and authorization mechanisms.
Directory enumeration risks: Attackers can easily discover and retrieve exposed files.
