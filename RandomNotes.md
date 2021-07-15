# Random Notes

- Permanent Generation :– This is the portion of Heap-memory that contains the JVM’s metadata for the runtime classes and application methods.
 If variable or method is not changed for every new object creation those cannot be stored in a normal heap, 
 they are stored in a special area called permanent generation(PermGen).
 The main difference is that the heap is the auto growing space, with RAM memory as its constraints, 
 whereas this PermGen has a fixed space allocation, and this is shared with all the instances.From java8 its called **metaspace** and 
 from java 8 metaSpace is not    part of heapmemory

- Concurrent HashMap :- The underlined data structure for ConcurrentHashMap is Hashtable.
ConcurrentHashMap class is thread-safe i.e. multiple threads can operate on a single object without any complications.
At a time any number of threads are applicable for a read operation without locking the ConcurrentHashMap object which is not there in HashMap.
In ConcurrentHashMap, the Object is divided into a number of segments according to the concurrency level.
The default concurrency-level of ConcurrentHashMap is 16.
In ConcurrentHashMap, at a time any number of threads can perform retrieval operation but for updated in the object, the thread must lock the particular segment in which the thread wants to operate. This type of locking mechanism is known as Segment locking or bucket locking. Hence at a time, 16 update operations can be performed by threads.
Inserting null objects is not possible in ConcurrentHashMap as a key or value.

- Producer Consumer Problem
-  java.lang.OutOfMemoryError: Java heap space  and   java.lang.OutOfMemoryError: GC Overhead limit exceeded
-  Singelton - only one isntance of class should exists.
  
  To be safe from reflection check if instance is not null and return same instance if so.
  ````
  class Singleton{
   private Singleton(){}
   public static Singleton getInstance(){
     return SingletonHolder.INSTANCE;
     }
    private static class SingletonHolder {
       static final Singleton INSTANCE = new Singleton();
    }
  }
  ````
 - Garbage collection
   GC works in steps of mark , sweep/delete and compacting.GC clears memory in heap.
   
   Static variables and metadata of class are stored in permGen or metaspace.
   
   young generation will have eden , surviour 1 , surviour2 blocks . Reason for two surviours is to reduce compacting
   old generation.
   Types of GC - 1.serial.   2. parallel (prefered for low latency )      3. concurrent (prefered for throughput )
   
   G1GC is efficient one till now. which is garbage first garbagr collection.its combination of serial and parallel.It divides heap to many regions of new and old based on which has major garbage. it takes low pause for compactating. 
   
   Mostly GC needs to take pause for mark and sweep.
   
 - Covarient return types
   Covariant return, means that when one overrides a method, the return type of the overriding method is allowed to be a subtype of the overridden method's return type.
   Below gives compile time error at line 2 as String is not subtype of Interger.
   ```
   public  class Sample {
    public Integer m1(){
        return null;
    }
    }
    class Stest extends Sample{
    public String m1(){ //line 2
      return null;
    }
    }
 - Immutable collections
   An object is considered immutable if its state cannot change after it is constructed. After you create an immutable instance of a collection, it holds the same data as long as a reference to it exists.

```
In JDK 8:

List<String> stringList = Arrays.asList("a", "b", "c");
stringList = Collections.unmodifiableList(stringList);

In JDK 9:

List stringList = List.of("a", "b", "c");
```
- What is starvation?

 Starvation is a situation when some threads acquired the shared resources for long time and therefore other threads are not able to access those resources and not able to do anything further.
  In Java, Starvation can be caused by inappropriate allocation of thread priorities.
  A thread with low priority can be starved by the threads of higher priority if the higher priority threads do not release shared resources time to time.
  
- What happens if we invoke run method without calling the start method for a thread instance?
  If we invoke run method without calling the start method for a thread instance, the code in run() method wil not be executed by a new thread but it will be executed by the existing thread only.

- Can you start a thread twice? : NO , it will give illegal state exception
- Why wait, notify and notifyAll are not inside thread class? : Java provides lock at object level not at thread level. Every object has lock, which is acquired by thread. Now if thread needs to wait for certain lock it make sense to call wait() on that object rather than on that thread.
- Blocking Queue 
  A Queue that additionally supports operations that wait for the queue to become non-empty when retrieving an element, and wait for space to become available in the queue when storing an element.
  BlockingQueue implementations are thread-safe.
  A BlockingQueue does not accept null elements.. All methods of BlockingQueue are atomic in nature and use internal locks.
- What is a factory method 
   factory method pattern is a creational pattern that uses factory methods to deal with the problem of creating objects without having to specify the exact class of the object that will be created.
- Optional class
  - Container object which may or maynot have value. if present get() will return value and ifpresent() returns true.This have methods to call someother method if not present , throw exception if not present ,filter and map methods.
  - Optional is final class and not serializable.
  - General idea for this is ot have return type where we can check if value is present else return default value or throw exception.
  
