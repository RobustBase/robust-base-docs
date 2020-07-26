# Dependency Inversion Principle (DIP)
---

According to Dependency Inversion Principle:
- High-level modules should not depend on low-level modules. Both should depend on abstractions.
- Abstractions should not depend on details.  Details should depend on abstractions.

> The best and easiest way to understand any of the design principles is to first have a look at the solution desing which **violates the design principle** and understand it's drawbacks then design the solution which **adheres to the design principle** and understand it's benefits.

## Example
Let's try to unserstand this by one example of **Notification App** which sends out notifications via different mode like email and SMS. As the step by step approach we will first design this solution which violates the DIP and then after uncovering the drawbacks of bad design we will redesign our solution which adheres to the DIP and undesrstand how it solves the problems.

## Solution Design: Violation of DIP

## Solution Re-Design: Adhering the DIP