# API Test Framework

A Java-based API test automation framework using Rest Assured, JUnit 5, and ExtentReports for reporting.

## Features
- REST API testing with Rest Assured
- Test execution and assertions with JUnit 5
- Rich HTML reporting with ExtentReports
- Configurable via properties files
- Easy integration with CI/CD tools like Jenkins

## Project Structure
```
apitestframework/
├── Jenkinsfile                # Jenkins pipeline configuration
├── pom.xml                    # Maven project file
├── src/
│   ├── main/
│   │   ├── java/              # (Reserved for main code, if needed)
│   │   └── resources/         # (Reserved for main resources)
│   └── test/
│       ├── java/
│       │   ├── config/        # Configuration management classes
│       │   ├── helpers/       # Helper classes for API and payloads
│       │   ├── reports/       # ExtentReports manager
│       │   └── tests/         # Test classes (e.g., LoginTests.java)
│       └── resources/         # Test resources (application.properties, logback.xml)
└── target/
    ├── ExtentReports.html     # Generated HTML test report
    └── surefire-reports/      # JUnit XML reports
```

## Getting Started

### Prerequisites
- Java 11 or higher
- Maven 3.6+
- (Optional) Jenkins for CI/CD

### Setup
1. **Clone the repository:**
   ```
   git clone <your-repo-url>
   cd apitestframework
   ```
2. **Configure properties:**
   - Edit `src/test/resources/application.properties` for environment-specific settings.

3. **Build and run tests:**
   ```
   mvn clean test
   ```
   - Test results will be available in `target/ExtentReports.html` and `target/surefire-reports/`.

### Running in Jenkins
- The included `Jenkinsfile` defines a pipeline for build and test.
- Ensure Jenkins has Maven and JDK installed (matching names in Jenkinsfile).
- Create a Pipeline job and point it to this repository.
- Test results and reports will be archived as build artifacts.

## Key Files
- `pom.xml` — Maven dependencies and build configuration
- `Jenkinsfile` — Jenkins pipeline definition
- `src/test/java/tests/LoginTests.java` — Example test class
- `src/test/java/helpers/ApiHelper.java` — API request helper
- `src/test/java/reports/ExtentManager.java` — ExtentReports setup
- `src/test/resources/application.properties` — Configurations

## Dependencies
- [Rest Assured](https://rest-assured.io/)
- [JUnit 5](https://junit.org/junit5/)
- [ExtentReports](https://extentreports.com/)
- [Jackson Databind](https://github.com/FasterXML/jackson-databind)
- [SLF4J](http://www.slf4j.org/), [Logback](http://logback.qos.ch/)

## Customization
- Add new test classes in `src/test/java/tests/`.
- Use helpers in `helpers/` for payloads and API calls.
- Update `application.properties` for different environments.

## Reporting
- After test execution, open `target/ExtentReports.html` in a browser for a detailed report.
- JUnit XML reports are in `target/surefire-reports/` for CI integration.

## Contributing
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes
4. Push to your fork and open a pull request

