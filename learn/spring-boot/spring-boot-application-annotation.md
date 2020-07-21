# `@SpringBootApplication` Annotation
---
`@SpringBootApplication` annotation is one of the most popular Spring Boot annotations. You can say it's one size fits to many, does lot of work for developer. More specifically it's combination of three annotations `@Configuration`, `@EnableAutoConfiguration` and `@ComponentScan`.

![SpringBootApplication-Annotation](https://docs.google.com/drawings/d/1qffIVIgO_wqexzgm7mCLY9xzJmuttTIFIcx346p0znc/export/png)


## `@Configuration` Annotation
---
`@Configuration` annotation allows developer to define Spring configuration in `Java-based` manner. As per recommendation application's primary source be a `@Configuration` class, usually the class which defines `main` method should be annotated with `@Configuration`.
- An application can have one or more `@Configuration` classes.
- In case of multi configuration classes, `@Import` can be used to import other configuration classes into primary configuration class.
- In case you have some `XML-based` configuration, `@ImportResource` can be used to import XML configuration files.

## `@EnableAutoConfiguration` Annotation
---
