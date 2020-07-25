# `ApplicationRunner` Inteface
---

```java
@Component
public class MyApplicationRunner implements ApplicationRunner {
    @Override
    public void run(ApplicationArguments args) throws Exception {
        System.out.println(args.getOptionNames());
        System.out.println(args.getOptionValues("key1"));
        System.out.println(args.getNonOptionArgs());
    }
}
```

## Pass Program Arguments
- `foo` `bar` `--key1=value1` `--key2=value2` `--key2=value3`