# Spring Security Basic Authentication

A Spring Boot application demonstrating basic authentication implementation using Spring Security. This project showcases form-based login with in-memory user authentication.

Originally adopted from: https://spring.io/guides/gs/securing-web

## Features

- Form-based authentication using Spring Security
- In-memory user authentication
- Protected and public pages
- Custom login page with Thymeleaf templates
- Logout functionality
- Spring Boot 3.4.3 with Java 21

## Technologies Used

- **Spring Boot 3.4.3** - Application framework
- **Spring Security** - Authentication and authorization
- **Thymeleaf** - Server-side template engine
- **Gradle** - Build automation tool
- **Java 21** - Programming language

## Prerequisites

Before running this application, ensure you have the following installed:

- Java 21 or higher
- Gradle (or use the included Gradle wrapper)

## How to Run

### Using Gradle Wrapper (Recommended)

1. **Clone the repository** (if not already cloned)
   ```bash
   git clone <repository-url>
   cd spring-security-basic
   ```

2. **Run the application**
   ```bash
   ./gradlew bootRun
   ```

   On Windows:
   ```bash
   gradlew.bat bootRun
   ```

3. **Access the application**

   Open your browser and navigate to: `http://localhost:8080`

### Using Gradle (if installed globally)

```bash
gradle bootRun
```

### Building a JAR and Running

1. **Build the project**
   ```bash
   ./gradlew build
   ```

2. **Run the JAR file**
   ```bash
   java -jar build/libs/spring-security-basic-0.0.1-SNAPSHOT.jar
   ```

## Default Credentials

The application uses in-memory authentication with the following default credentials:

- **Username:** `user`
- **Password:** `password`

> **Note:** These credentials are defined in `WebSecurityConfig.java` and are for demonstration purposes only. In production, use a proper user store and secure password encoding.

## Application Pages

- **`/` or `/home`** - Public home page (no authentication required)
- **`/landing`** - Protected landing page (requires authentication)
- **`/login`** - Custom login page

## Project Structure

```
spring-security-basic/
├── src/
│   ├── main/
│   │   ├── java/com/example/springsecuritybasic/
│   │   │   ├── SpringSecurityBasicApplication.java  # Main application class
│   │   │   ├── WebSecurityConfig.java              # Security configuration
│   │   │   └── MvcConfig.java                      # MVC configuration
│   │   └── resources/
│   │       ├── templates/
│   │       │   ├── home.html                       # Home page template
│   │       │   ├── login.html                      # Login page template
│   │       │   └── landing.html                    # Protected page template
│   │       └── application.properties              # Application configuration
│   └── test/
│       └── java/com/example/springsecuritybasic/
│           └── SpringSecurityBasicApplicationTests.java
├── build.gradle                                     # Gradle build configuration
└── settings.gradle                                  # Gradle settings
```

## How It Works

1. **WebSecurityConfig.java** - Configures Spring Security:
   - Allows public access to `/` and `/home`
   - Requires authentication for all other requests
   - Configures form-based login with custom login page
   - Sets up in-memory user with USER role

2. **MvcConfig.java** - Configures view controllers for mapping URLs to Thymeleaf templates

3. **Thymeleaf Templates** - Render HTML pages with Spring Security integration

## Running Tests

To run the tests:

```bash
./gradlew test
```

## Stopping the Application

Press `Ctrl + C` in the terminal where the application is running.

## Troubleshooting

- **Port 8080 already in use:** Change the port by adding `server.port=8081` to `application.properties`
- **Java version error:** Ensure you have Java 21 or higher installed (`java -version`)

## License

This project is for educational purposes based on Spring's official guide.
