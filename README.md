# Admin Server

A Spring Boot Admin Server for monitoring and managing Spring Boot microservices.

## Overview

The **admin-server** provides a beautiful UI dashboard to visualize health status, metrics, logs, environment properties, and more from all registered Spring Boot applications via Eureka and Actuator endpoints.

## Tech Stack

- Java 21
- Spring Boot Admin Server
- Spring Boot Actuator
- Eureka Discovery Client
- Gradle (Kotlin DSL)

## Getting Started

1.  **Clone the Repository:**

    ```bash
    git clone [https://github.com/abijith-suresh/admin-server.git](https://github.com/abijith-suresh/admin-server.git)
    ```

2.  **Navigate to the project:**

    ```bash
    cd admin-server
    ```

3.  **Configuring Clients:**

    To allow your microservices to be monitored, add the following to each service:

    **Dependencies**

    ```kotlin
    implementation("de.codecentric:spring-boot-admin-starter-client")
    implementation("org.springframework.boot:spring-boot-starter-actuator")
    ```

    **Configuration**

    ```yaml
    spring:
      boot:
        admin:
          client:
            url: http://localhost:9090

    management:
      endpoints:
        web:
          exposure:
            include: "*"
    ```

4.  **Run the application:**

    ```bash
    ./gradlew bootRun
    ```

## License

This project is licensed under the MIT License.
