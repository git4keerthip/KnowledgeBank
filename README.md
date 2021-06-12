# Interview Questions Collections

## Tech Mahindra

- What is a class loader?

  Class loaders are responsible for loading Java classes during runtime dynamically to the JVM (Java Virtual Machine). Also, they are part of the JRE (Java Runtime Environment). Hence, the JVM doesn't need to know about the underlying files or file systems in order to run Java programs thanks to class loaders.
  Also, these Java classes aren't loaded into memory all at once, but when required by an application.We can have a custom class loader also my extending **ClassLoader** class and overriding **findClass()** method.
  
- Difference between FailFast and FailSafe?

  Fail-Fast iterators immediately throw ConcurrentModificationException if there is structural modification of the collection. Structural modification means adding, removing any element from collection while a thread is iterating over that collection. 
  Iterator on ArrayList, HashMap classes are some examples of fail-fast Iterator.
  Fail-Safe iterators don’t throw any exceptions if a collection is structurally modified while iterating over it. 
  This is because, they operate on the clone of the collection, not on the original collection and that’s why they are called fail-safe iterators. Iterator on CopyOnWriteArrayList, ConcurrentHashMap classes are examples of fail-safe Iterator.

- Difference between sleep() and wait() in Threads
  
- Can we write try catch in constructor
- Object class methods
- Can List<String> be passed to List<Object>
- Difference between List and Set
- Will Java Interface has variables -> yes they are static and final
- What are generics
- Any design pattern example
- Spring autowiring meaning
- difference between @component @restcontroller @controller
- Synchronized in Java
- Can we use super() and this() at a time. ->no , ll get compile time error as both has to first statement in java.
