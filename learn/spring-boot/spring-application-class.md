# `SpringApplication` Class
---
`SpringApplication` class provides simplest way to bootstrap and launch Spring application just by executing Java `main` method. The good old way of running Java programs, here It allows to bring up an application itself by running `main` method.

In order to bootsrap the application `SpringApplication` class:
- Creates an appropriate `ApplicationContext` instance.
- Registera a `CommandLinePropertySource` to expose command line arguments as Spring properties.
- Refreshes the application context, loads all singleton beans.
- Triggers `CommandLineRunner` beans if any.

```java
 @SpringBootApplication
 public class MyApplication  {

   // ... Bean definitions goes here

   public static void main(String[] args) {
     SpringApplication.run(MyApplication.class, args);
   }
 }
```
