# Chaldal E-Commerce Website QA & Testing Strategy
This repository outlines a comprehensive Quality Assurance (QA) and testing framework for the Chaldal e-commerce platform. This repository includes manual test case scenarios , automated regression suites built using Selenium WebDriver and the Page Object Model (POM) , API testing workflows , performance load testing , and robust security testing protocols.

## Disclaimer: This repository, along with its testing frameworks and strategies, is developed strictly for academic purposes.

---

# Chaldal
Chaldal is a complex e-commerce platform that hosts over 15,000 products. It utilizes real-time inventory tracking across dozens of micro-warehouses and operates on a 1-hour delivery promise. In such a large-scale application, even a minor bug can cause delayed grocery deliveries or entirely break the checkout process. Therefore, implementing a robust QA strategy is absolutely critical to keep operations running smoothly.

---

# Testing Types Performed, Tools and Technologies Used

## Manual Testing & Bug Reporting

- We will validate both positive and negative user flows to ensure the customer user experience (UX) remains intuitive and smooth. Core user journeys—covering everything from the initial product search to successful delivery slot selection—will be thoroughly tested.


- Bug Reporting: If any unexpected behavior is identified, a structured bug report containing exact reproduction steps will be documented for the development team.


- Tools: Jira will be utilized for bug tracking and task management.

## Automation Testing (Selenium & POM)

- To eliminate the need for manually executing the entire test suite after minor code updates, automated regression suites will be deployed. This framework follows a design pattern that separates the website's visual UI components from the underlying test code. Locators and actions for essential pages—such as HomePage and CartPage—will be built to execute end-to-end checkout automation sequences.


- Tools: Selenium WebDriver paired with the Page Object Model (POM) design pattern.

## API Testing

- Chaldal depends heavily on microservices (such as separate services for user authentication, inventory management, and payment processing), meaning we must verify that data flows safely and accurately between the frontend interface and backend servers. This involves backend inventory validation via the /api/v1/inventory endpoint and verifying payment API response status codes (e.g., 200 OK for success and 400 Bad Request for invalid signatures).


- Tools: Postman.

## Performance Testing

- E-commerce traffic tends to spike unpredictably during flash sales, evening rush hours, or prior to major festivals like Ramadan and Eid; we will check if the server remains stable under heavy traffic. Load testing will verify if the system can seamlessly handle 20,000 concurrent users browsing and adding items to their carts, while stress testing will pinpoint the server's definitive breaking point to ensure it fails gracefully rather than crashing completely.


- Tools: JMeter or Locust will be utilized to simulate thousands of concurrent shoppers hitting the platform simultaneously.

## Security Testing

- Robust validation protocols will be executed to protect personal customer details, delivery addresses, and digital payment methods (such as bKash, Nagad, and credit cards) from financial fraud. This includes verifying payment tampering protections (ensuring a malicious actor cannot modify transaction values during the gateway handshake) and assessing input sanitization across search fields and login inputs against SQL Injection (SQLi) and Cross-Site Scripting (XSS) threats.

- Tool: OSAP ZAP
