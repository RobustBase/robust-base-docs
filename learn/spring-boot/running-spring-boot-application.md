# Running Spring Boot Application
One of the biggest advantages of packaging your application as a jar and using an embedded HTTP server is that you can run your application as you would any other. 
Debugging Spring Boot applications is also easy. You do not need any special IDE plugins or extensions.

---

## Running from an IDE
- Import Spring Boot project in the IDE
- Run as simple Java application (file having `main` method)

---

## Running as a Packaged Application
- `java -jar target/myapplication-0.0.1-SNAPSHOT.jar`
- Remote debugging
  `java -Xdebug -Xrunjdwp:server=y,transport=dt_socket,address=8000,suspend=n -jar target/myapplication-0.0.1-SNAPSHOT.jar`
  
---

## Using the Maven Plugin

---

## Using the Gradle Plugin
