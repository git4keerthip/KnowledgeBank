# Interview Questions Collections

## TM

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
- Can List< String > be passed to List< Object >
- Difference between List and Set
- Will Java Interface has variables -> yes they are static and final
- What are generics
- Any design pattern example
- Spring autowiring meaning
- difference between @component @restcontroller @controller
- Synchronized in Java
- Can we use super() and this() at a time. ->no , ll get compile time error as both has to first statement in java.
- Can class be static in java
  YES, we can have static class in java. In java, we have static instance variables as well as static methods and also static block. 
  Classes can also be made static in Java. we can’t make Top-level (outer) class static. Only nested classes can be static. 
  
- Volatile Keyword in java 
  Volatile keyword is used to modify the value of a variable by different threads. It is also used to make classes thread safe. 
  It means that multiple threads can use a method and instance of the classes at the same time without any problem.
  <additional> volatile satisifies visibility but not mutual exclusion ,but synchronized satisfies both.
    
 ## >
- What is composition and example
- New feature in Java 8 Interface , how it is useful
- Inheritance usefulness for developers
- what is Spring IOC container
- Spring Bean life cycle
- Component scan in Spring
- Print permutations of a string
- Various status codes of Rest call , 100 , 200 , 300 , 400 , 500 series
- HTTP status codes 
  ````
  1xx: Informational – Communicates transfer protocol-level information.
  2xx: Success – Indicates that the client’s request was accepted successfully.
  3xx: Redirection – Indicates that the client must take some additional action in order to complete their request.
  4xx: Client Error – This category of error status codes points the finger at clients.
  5xx: Server Error – The server takes responsibility for these error status codes.
  ````
