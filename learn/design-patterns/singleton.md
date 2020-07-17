# Singleton Design Pattern
---

## Motivation

Sometimes it's important to have only one instance for a class. For example, in a system there should be only one window manager (or only a file system or only a print spooler). Usually singletons are used for centralized management of internal or external resources and they provide a global point of access to themselves.

The singleton pattern is one of the simplest design patterns: it involves only one class which is responsible to instantiate itself, to make sure it creates not more than one instance; in the same time it provides a global point of access to that instance. In this case the same instance can be used from everywhere, being impossible to invoke directly the constructor each time.

---

## Intent
- Ensure that only one instance of a class is created.
- Provide a global point of access to the object.

---

```java
class Singleton {
	private static Singleton instance;

	private Singleton() {
		...
	}
	
	public static synchronized Singleton getInstance(){

		if (instance == null)
			instance = new Singleton();

		return instance;
	}
	
	...
	
	public void doSomething()
	{
		...
	}
}
```
