# OWASP Juice Shop – Admin Section Challenge

In this challenge of OWASP Juice Shop, the objective was to discover and access the hidden administration panel. This challenge highlights weaknesses in access control where sensitive functionality is exposed through discoverable client-side routes.

## Initial Analysis

By inspecting the routes from the client side, it is sometimes possible to uncover hidden or restricted areas such as administrative panels.

## Steps taken to solve this challenge 
1. Source Code Analysis -
Opened browser Developer Tools and inspected the frontend JavaScript files, particularly main.js.
Identified route definitions within the application, including a path referencing an administration section.
![path](https://github.com/user-attachments/assets/f3c61fd8-0ad3-4b32-ba6f-c57e89bfa9d8)

2. Direct Path Access
Entered the discovered route directly into the browser : http://192.168.123.3000/#/administration
![adminsection](https://github.com/user-attachments/assets/fbc7d8b8-5e6e-4eb6-a112-8641ef0fd620)

3. Gain Administrative Access
If the login fails, by using SQL injection, authentication can be bypassed.

## Solution Explanation
The challenge was solved by discovering a hidden administrative route through client-side code inspection and then accessing it with appropriate credentials. The application relied on obscurity of the route rather than enforcing strict access control measures, making it easy to discover sensitive functionality.

## Tools used
- Web browser
- Browser developer tools
