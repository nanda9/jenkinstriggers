# Repository Guide

## Project
- Java web application packaged as a WAR (`com.visualpathit:vprofile`).
- Maven is the build system; `pom.xml` configures Java source and target level 17.
- The application uses Spring MVC, Spring Security, Spring Data JPA, JSP, and integrations including MySQL, RabbitMQ, Memcached, and Elasticsearch.
- Application code and resources are under `src/main`; tests are under `src/test`.
- The README lists JDK 11, but the Maven compiler configuration currently requires Java 17. Treat `pom.xml` as authoritative unless the build configuration changes.

## Common Commands
- Run unit tests: `mvn test`
- Build and package the WAR: `mvn clean package`
- Run the application with the configured Jetty plugin: `mvn jetty:run`
- Run the Jenkins integration-test phase locally: `mvn verify -DskipUnitTests`

The application may need external services and local configuration to run or pass integration tests. Jenkins stages for SonarQube and Nexus also depend on Jenkins plugins, credentials, and configured servers; do not assume they are available locally.

## Working Guidance
- Keep changes focused and follow the existing Java and Maven conventions.
- Add or update tests under `src/test` for behavior changes.
- Do not commit generated `target/` output.
- Avoid changing deployment or service configuration unless the task requires it.