WebhookApp – SQL Webhook Integration (Java + Spring Boot)

Overview

This application interacts with a remote API to:

1. Generate a Webhook URL and Access Token.


2. Dynamically choose an SQL query based on the regNo value.


3. Submit the final query securely to the provided webhook.




---

Tech Stack

Java 17+

Spring Boot 3.5.5

Maven for dependency management

RestTemplate for HTTP communication



---

Project Structure

.
├── pom.xml                # Maven configuration
├── src/                   # Source code (controllers, services, models)
├── HELP.md                # Maven help file
├── mvnw / mvnw.cmd        # Maven wrapper
└── .gitignore             # Git ignore rules


---

How It Works

1. Sends a POST request to https://bfhldevapigw.healthrx.co.in/hiring/generateWebhook/JAVA.


2. Receives a webhook URL & access token.


3. Extracts last two digits from regNo:

If odd → Executes Query 1.

If even → Executes Query 2.



4. Sends final SQL query back to webhook endpoint.




---

How to Run

mvn clean package
mvn spring-boot:run -DskipTests


---

Key Files

WebhookService.java – Core logic to handle API calls and SQL query submission.

WebhookResponse.java – Model for webhook response.

pom.xml – Dependencies & build configuration.



---

License

This project is for educational and hiring evaluation purposes.
