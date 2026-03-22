## OWASP Juice Shop – Exposed Metrics Challenge

In the Exposed Metrics challenge of OWASP Juice Shop, the objective was to discover an exposed metrics endpoint that reveals sensitive system information. This challenge demonstrates how improperly exposed monitoring endpoints can leak operational data.

Web applications like Juice Shop can be configured to expose operational metrics for monitoring systems such as Prometheus. By default, Prometheus exposes metrics at the `/metrics` endpoint. These metrics include server statistics, CPU and memory usage, runtime details, and other operational data. If publicly accessible, this information can be sensitive and potentially aid attackers.

<img width="1770" height="61" alt="image" src="https://github.com/user-attachments/assets/6e605ba7-fe42-49a9-8371-37c15a2dd1fe" />

<img width="1786" height="1070" alt="image" src="https://github.com/user-attachments/assets/5b0929e2-fe01-452c-9eca-6db6ecc8a550" />

---

## Steps Taken to Solve the Challenge

1. **Identify the Monitoring System**  
  Recognized that Juice Shop uses Prometheus for metrics collection and reviewed Prometheus documentation to understand default configurations.

2. **Access the Metrics Endpoint**  
  Navigated to the default Prometheus metrics endpoint in the browser:  
  `http://192.168.123.111:3000/metrics`

3. **Analyze Exposed Data**  
  Examined the data displayed at the endpoint, which included:
  - Startup times for various services  
  - CPU and memory usage statistics  
  - Runtime and system health information  
  - File upload details, including types and success/failure counts  

---

## Solution Explanation

The challenge was solved by accessing the default `/metrics` endpoint. The exposed data revealed operational and system-level information that could be leveraged by an attacker, demonstrating the security risk of leaving monitoring endpoints publicly accessible.

---

## Tools Used

- Web browser  
- Knowledge of Prometheus monitoring and default configurations  

---

## What This Teaches About Security

- **Sensitive operational data exposure**  
  Exposing metrics publicly can leak critical system information.

- **Default configurations matter**  
  Leaving default monitoring endpoints accessible can create vulnerabilities.

- **Secure monitoring practices**  
  Metrics endpoints should be restricted to authorized users and protected from public access.
