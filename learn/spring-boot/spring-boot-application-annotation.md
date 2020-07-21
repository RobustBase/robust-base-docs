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
Spring Boot auto-configuration attempts to automatically configure your Spring application based on the jar dependencies that you have added. For example, if HSQLDB is on your classpath, and you have not manually configured any database connection beans, then Spring Boot auto-configures an in-memory database.

You need to opt-in to auto-configuration by adding the @EnableAutoConfiguration or @SpringBootApplication annotations to one of your @Configuration classes.

### Replacing Auto-configuration
Auto-configuration is non-invasive. At any point, you can start to define your own configuration to replace specific parts of the auto-configuration. For example, if you add your own DataSource bean, the default embedded database support backs away.

If you need to find out what auto-configuration is currently being applied, and why, start your application with the --debug switch. Doing so enables debug logs for a selection of core loggers and logs a conditions report to the console.

### Disabling Specific Auto-configuration Classes
If you find that specific auto-configuration classes that you do not want are being applied, you can use the exclude attribute of @SpringBootApplication to disable them, as shown in the following example:

```java
import org.springframework.boot.autoconfigure.*;
import org.springframework.boot.autoconfigure.jdbc.*;

@SpringBootApplication(exclude={DataSourceAutoConfiguration.class})
public class MyApplication {
}
```

If the class is not on the classpath, you can use the `excludeName` attribute of the annotation and specify the fully qualified name instead. If you prefer to use `@EnableAutoConfiguration` rather than `@SpringBootApplication`, `exclude` and `excludeName` are also available. Finally, you can also control the list of auto-configuration classes to exclude by using the `spring.autoconfigure.exclude property`.

## `@ComponentScan` Annotation
---
Configures component scanning directives for use with `@Configuration` classes. Provides support parallel with Spring XML's `<context:component-scan>` element.

Either `basePackageClasses()` or `basePackages()` (or its alias `value()`) may be specified to define specific packages to scan. If specific packages are not defined, scanning will occur from the package of the class that declares this annotation.

Note that the `<context:component-scan>` element has an `annotation-config` attribute; however, this annotation does not. This is because in almost all cases when using `@ComponentScan`, default annotation config processing (e.g. processing `@Autowired` and friends) is assumed. Furthermore, when using `AnnotationConfigApplicationContext`, annotation config processors are always registered, meaning that any attempt to disable them at the `@ComponentScan` level would be ignored.
