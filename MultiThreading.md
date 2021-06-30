# MultiThreading

- Executors class :- provides factory and utility methods for below interfaces and classes. Methods are all static in this.
- Executor interface :- Interface that executes submited runnable tasks. Execution might not be strictly asynchronous.
   Reduces overhead of creating new threads and scheduling them. Has one method *void execute(Runnable r)*.
- ExecutorService interface :- Executor Interface that can terminate the tasks and has methods returning future object to track progress of one/more async tasks
  Overriden *execute(Runnable r) method will return future object to track tasks status*.
- Lock Interface :- Lock implementations provide more extensive locking operations than can be obtained using synchronized methods and statements.
   With synchronous multiple locks acquired has to be released in reverse order and in same lexical scope
   With Lock interface we can acquire and release locks in multiple order and in different scopes.We dont explicitly need to call unlock() like in Lock.
   Operations done after lock() must be done in try-catch /try-final way to ensure lock is released when unnecessary.
- Reetrant Lock Class:- Lock with exteneded features.
- Condition :- Where a Lock replaces the use of synchronized methods and statements, a Condition replaces the use of the Object monitor methods(wait, notify,     notifyAll)
- Callable Interface:- The Callable interface is similar to Runnable, in that both are designed for classes whose instances are potentially executed by another thread. A        
   Runnable, however, does not return a result and cannot throw a checked exception.
- Future Interface :- A Future represents the result of an asynchronous computation. Methods are provided to check if the computation is complete, to wait for its  
  completion, and to retrieve the result of the computation. The result can only be retrieved using method get when the computation has completed,
