# Dependency Inversion Principle (DIP)
---

According to Dependency Inversion Principle:
- High-level modules should not depend on low-level modules. Both should depend on abstractions.
- Abstractions should not depend on details.  Details should depend on abstractions.

> The best and easiest way to understand any of the design principles is to first have a look at the solution desing which **violates the design principle** and understand it's drawbacks then design the solution which **adheres to the design principle** and understand it's benefits.

Let's try to unserstand this by one example of **Notification App** which sends out notification to via different mode like email and SMS.