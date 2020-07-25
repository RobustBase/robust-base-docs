# `CommandLineRunner` Inteface
---

```java
@Component
public class MyCommandLineRunner implements CommandLineRunner {
    @Override
    public void run(String... args) throws Exception {
        for (String arg : args) {
            System.out.println(arg);
        }
    }
}
```

## Pass Program Arguments
- `foo` `bar` `--key1=value1` `--key2=value2` `--key2=value3`