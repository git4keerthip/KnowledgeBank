# Random Notes

- Permanent Generation :– This is the portion of Heap-memory that contains the JVM’s metadata for the runtime classes and application methods.
 If variable or method is not changed for every new object creation those cannot be stored in a normal heap, 
 they are stored in a special area called permanent generation(PermGen).
 The main difference is that the heap is the auto growing space, with RAM memory as its constraints, 
 whereas this PermGen has a fixed space allocation, and this is shared with all the instances.From java8 its called **metaspace**
