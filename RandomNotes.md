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
  To be safe from reflection check if instance is not null and return same insstance if so.
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
  
