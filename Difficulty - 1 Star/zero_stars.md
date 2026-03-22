## OWASP Juice Shop – Zero Stars Challenge

In the Zero Stars challenge of OWASP Juice Shop, the objective was to interact with the application in a way that results in a zero-star rating being recorded.

To achieve this, the rating system was analyzed using browser Developer Tools. By inspecting network requests and client-side code, the API endpoint responsible for submitting product reviews was identified. The request payload was then manipulated to manually submit a review with a rating value of **0**, even though the application’s interface does not normally allow selecting a zero-star rating.

This bypassed the frontend validation and allowed the challenge to be completed successfully.
<img width="1660" height="79" alt="image" src="https://github.com/user-attachments/assets/3e6a933f-4e54-4ad3-9274-884a7caa6538" />

---

## Steps Taken to Solve the Challenge

1. **Analyze the Rating System**  
  Used Developer Tools to inspect how ratings are submitted.

2. **Identify the API Endpoint**  
  Located the request responsible for sending review data.

3. **Modify the Request Payload**  
  Manually changed the rating value to `0` before sending the request.

<img width="1193" height="1086" alt="image" src="https://github.com/user-attachments/assets/10256c2d-cf83-4a84-b2c3-fcde4fea5565" />

4. **Submit the Request**  
  Sent the modified request and observed that the zero-star rating was accepted.

---

## Tools Used

- Chrome Developer Tools (Network tab)  
- Request interception and modification (manual payload editing)  

---

## What This Teaches About Security

- **Client-side validation can be bypassed**  
  Restrictions enforced in the UI (like minimum rating values) are not secure.

- **Input validation must be enforced server-side**  
  The backend should reject invalid values such as a zero rating if it is not allowed.

- **APIs are a common attack surface**  
  Attackers can directly interact with endpoints without using the intended interface.
