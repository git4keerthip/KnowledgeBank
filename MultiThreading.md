# MultiThreading

- Executors class :- provides factory and utility methods for below interfaces and classes. Methods are all static in this.
- Executor interface :- Interface that executes submited runnable tasks. Execution might not be strictly asynchronous.
   Reduces overhead of creating new threads and scheduling them. Has one method *void execute(Runnable r)*.
- ExecutorService interface :- Executor Interface that can terminate the tasks and has methods returning future object to track progress of one/more async tasks
  Overriden *execute(Runnable r) method will return future object to track tasks status*.
- Callable :- 
- Future :-
