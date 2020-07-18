# Running Spring Boot Application
One of the biggest advantages of packaging your application as a jar and using an embedded HTTP server is that you can run your application as you would any other. 
Debugging Spring Boot applications is also easy. You do not need any special IDE plugins or extensions.

---

## Running from an IDE
- Import Spring Boot project in the IDE
- Run as simple Java application (file having `main` method)

---

## Running as a Packaged Application
- Create executable JAR
  - **Maven**: `mvn clean install`
  - **Gradle**: `gradle clean build`
- Execute Java JAR
  - `java -jar target/myapplication-0.0.1-SNAPSHOT.jar`
- Remote debugging
  - `java -Xdebug -Xrunjdwp:server=y,transport=dt_socket,address=8000,suspend=n -jar target/myapplication-0.0.1-SNAPSHOT.jar`
  
---

## Using the Maven Plugin
The Spring Boot Maven plugin includes a `run` goal that can be used to quickly compile and run your application. Applications run in an exploded form, as they do in your IDE. The following example shows a typical Maven command to run a Spring Boot application:

```bash
mvn spring-boot:run
```

---

## Using the Gradle Plugin
The Spring Boot Gradle plugin also includes a `bootRun` task that can be used to run your application in an exploded form. The bootRun task is added whenever you apply the `org.springframework.boot` and java plugins and is shown in the following example:

```bash
gradle bootRun
```
