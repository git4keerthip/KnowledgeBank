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
- Stateless and stateful differences
  
## MS
- exceptions from child ovveriding methods when parent ovveriden method has no exception thrown
- parent class methos has void return type, child class ovveriding method has int return type
- parent class(A) static method(m1) is overiden in child class (B) :- A a = new B() ; a.m1(); will call parent classmethod
- Different between abstract and interface
- Can a abstract class have constructor , yes but it cant be instantiated. Abstract class constructor will be called from child class.
- advantages of default methods in interface.
- when do we use abstract class and when we use interfaces.
- Disadvantages of having a static varaible, where do this static variables will be stored
    Static variables are similar to global variables,below are reason to avoid static
    - Because there's exactly one instance per JVM, 
    - Static variables are difficult to control access to.  so they can be changed by parts of your program when you don't expect it.
    - Serialization doesn't work well with static. During deserialization static are not touched at all as they belong to class
- scenrios when hashcode is not overiden and equals returns always true,insert 10 elements in hashset , whats the size.
- scenario when hashcode returns always 1 and equals returns true , insert 10 elements in hashset  what is size.
- Volatile keyword
- Difference between failfast and failsafe
- Difference between hashtable and hashmap, why hashtable wont allow null.
  - HashTable calls key.hashcode() in put() passing null withh throw NPE , as null is not object
  - HashMap checks for null and return 0 as hash if not null it calculates hashcode().
- internal working of concurrentHashMap, some questions on this.
- Maintain insertion order and a store key value pair , which data structure.
- How retirval happens in hashMap , whats new change in java8 - redblack tree and how it improves retrieval.
- calling start two times on same thread. few scenarios here, by calling run() without run()ovverding . calling start() with ovverring run()
- class extends thread butdidnt ovveride run() :- programs runs as usual , no compile error
- Left join in SQL
- sort array with 0's and 1's in O(n).
- why serialUid is used , what happens if its not declared.
  When an object of a class is first serialized, a class descriptor containing among other things the class name and serial version UID is written to the stream.       
  When this is deserialized, the JVM checks if the serial version UID read from the stream is the same as loaded class. If they're not, it doesn't      
  even try to deserialize the object, because it knows the classes are incompatible. JVM will create internal a serialUID and this is compiler dependent and may   
  give a Illegalcast exception.
  - Serial versions of different classes are independent and do not interfere each other.serialVersionUID is needed to remember versions of the class. It is not  
    necessary for two classes to have unique values.
- Write immutable class
- Future in threads.
- Hacker rank - 2 Sum , Longest increasig sub array 

