# SpringNotes




---

# Day 1: Introduction to Spring Boot

## Overview

### What is Spring Boot?
Spring Boot is an open-source framework that simplifies the development of production-ready applications. It is built on top of the Spring Framework and provides a wide range of features to streamline the setup, configuration, and development of Spring applications.

### Key Features of Spring Boot
- **Standalone Applications**: Spring Boot applications can run independently using an embedded server (e.g., Tomcat, Jetty).
- **Embedded Servers**: No need to deploy WAR files; Spring Boot uses embedded servers.
- **Opinionated 'Starter' Dependencies**: Simplifies dependency management by providing a set of pre-configured dependencies.
- **Production-Ready Features**: Includes metrics, health checks, and externalized configuration.
- **Easy Configuration**: Uses sensible defaults and annotations to reduce the need for boilerplate configuration.

## Setting Up Your Development Environment

### Prerequisites
- **Java Development Kit (JDK)**: Ensure you have JDK 8 or higher installed.
- **Integrated Development Environment (IDE)**: Use an IDE such as IntelliJ IDEA, Eclipse, or VSCode.

### Creating a Spring Boot Project

1. **Using Spring Initializr**
   - Go to [Spring Initializr](https://start.spring.io/)
   - Fill in the project metadata:
     - **Project**: Maven or Gradle
     - **Language**: Java
     - **Spring Boot**: Latest stable version
     - **Project Metadata**: Group, Artifact, Name, etc.
     - **Dependencies**: Add 'Spring Web' for a web application.
   - Click **Generate** to download the project as a ZIP file.
   - Extract the ZIP file and open the project in your IDE.

2. **Manually Creating the Project**
   - You can also create a project manually using your build tool of choice (Maven/Gradle). Here's a basic example using Maven:

     ```xml
     <project xmlns="http://maven.apache.org/POM/4.0.0"
              xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
              xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
         <modelVersion>4.0.0</modelVersion>
         <groupId>com.example</groupId>
         <artifactId>demo</artifactId>
         <version>0.0.1-SNAPSHOT</version>
         <parent>
             <groupId>org.springframework.boot</groupId>
             <artifactId>spring-boot-starter-parent</artifactId>
             <version>2.5.4</version>
             <relativePath/> <!-- lookup parent from repository -->
         </parent>
         <dependencies>
             <dependency>
                 <groupId>org.springframework.boot</groupId>
                 <artifactId>spring-boot-starter-web</artifactId>
             </dependency>
         </dependencies>
         <build>
             <plugins>
                 <plugin>
                     <groupId>org.springframework.boot</groupId>
                     <artifactId>spring-boot-maven-plugin</artifactId>
                 </plugin>
             </plugins>
         </build>
     </project>
     ```

## Writing Your First Spring Boot Application

### Main Application Class
This is the entry point of your Spring Boot application. The `@SpringBootApplication` annotation denotes this class as the configuration class and enables auto-configuration.

```java
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class MySpringBootApplication {
    public static void main(String[] args) {
        SpringApplication.run(MySpringBootApplication.class, args);
    }
}
```

### Creating a Simple REST Controller
A REST controller handles HTTP requests and returns responses. Use the `@RestController` annotation to define a RESTful web service.

```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloController {
    @GetMapping("/hello")
    public String hello() {
        return "Hello, World!";
    }
}
```

### Running Your Application
- **From the IDE**: Run the `MySpringBootApplication` class as a Java application.
- **Using Maven**: Open a terminal, navigate to the project directory, and run `mvn spring-boot:run`.

### Testing Your Application
- Open a web browser and go to `http://localhost:8080/hello`.
- You should see the message `Hello, World!`.

---

This concludes your first day of learning Spring Boot. Feel free to ask any questions or seek clarification on any topics. Tomorrow, we'll dive into **Spring Boot Fundamentals**.
