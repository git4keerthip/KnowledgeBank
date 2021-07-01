# MultiThreading

- Executors class :- provides factory and utility methods for below interfaces and classes. Methods are all static in this.
- Executor interface :- Executes submited runnable tasks. Execution might not be strictly asynchronous.
   Reduces overhead of creating new threads and scheduling them. Has one method *void execute(Runnable r)*.
- ExecutorService interface :- Terminate the tasks and has methods returning future object to track progress of one/more async tasks
  Overriden *execute(Runnable r) method will return future object to track tasks status*.
- Lock Interface :- Lock implementations provide more extensive locking operations than can be obtained using synchronized methods and statements.
   With synchronous multiple locks acquired has to be released in reverse order and in same lexical scope
   With Lock interface we can acquire and release locks in multiple order and in different scopes.We dont explicitly need to call unlock() like in Lock.
   Operations done after lock() must be done in try-catch /try-final way to ensure lock is released when unnecessary.
- Reetrant Lock Class:- Lock with exteneded features.
- Condition :- Like Lock replaces the use of synchronized, a Condition replaces the use of the Object monitor methods(wait, notify, notifyAll)
- Callable<T> Interface:- The Callable interface is similar to Runnable, in that both are designed for instances potentially executed by another thread.        
   Runnable does not return a result and cannot throw a checked exception, Callable does.
- Future<T> Interface :- A Future represents the result of an asynchronous operation. Methods are provided to check if taks is complete, to wait for its  
  completion, and to retrieve the result. The result can only be retrieved using get() when the computation has completed.
- Semaphore Class:- Semaphores are  used to restrict the number of threads than can access aresource.Before execution each thread will acquire permit and release it once completes, else threads will be blocked till it gets permit. acquire() decreases count , release() increases count().
- for void methods in callable 
      future<?> and Callable<Void> and return null
