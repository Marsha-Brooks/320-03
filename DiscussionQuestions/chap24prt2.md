C# Discussion Questions /PINQ 
Chapter 24 from 575-600
1. What are the two scenarios in which you can use PLINQ to speed up operations? Why does using PLINQ in these scenarios speed up processing? 
Two scenarios in which you can use PLINQ to speed up operations are to parallelize a LINQ query over a simple collection.  Elements in a collection can be divided into a number of partitions the exact number depend on the current load of the computer and number of CPUS available. The elements in each partition can be processed by a separate thread.  The results are then merged.
The second scenario is to parallelize a LINQ query that joins two collections.  A query that joins two arrays in memory.
 2. How does AsParallel qualify as an extension method? First, explain what an extension method is and how you define extension methods, and them explain why AsParallel qualifies as an extension method. 
An extension method allows you to extend an existing type with additional static methods.  These static methods become immediately available to your code in any statements that reference data of the type being extended.  You define an extension method in a static class and specify the type to which the method applies as the first parameter in the method, along with this keyword.  An example of an extension method is as follows:
Int x = 591;
Console.WriteLine($”x.Negae {x.Negate()}”);

As Parallel qualifies as an extension method because it extends the ParallelQuery class. 
3. How do you cancel a PLINQ query before it finishes? Be specific with respect to the variables and methods used for the cancellation operation, and how the variables and methods are used.
You cancel a PLINQ query before it finishes specifying a CancellationToken object from a CcancellationTokenSource and use the WithCancellation extension method of the parallel Query.
 4. Why is it important to synchronize concurrent access to a server? Give an example of a specific condition that will cause an error in your application if concurrent access is not synchronized.
It is important to synchronize concurrent access to a server in order to ensure that tasks coordinate their activities correctly to prevent overlapping operations that might corrupt the data and cause bugs in the process. 
 5. What does the lock statement do?
The lock statement guarantees exclusive access to resources. The lock statement attempts to obtain a mutual-exclusion lock over the specified object and blocks if the same object is currently locked by another thread.  When the thread obtains the lock, the code in the block following the lock statement runs.  At the end of the block, the lock is released.  Threads that were previously blocked waiting for the lock then grab the lock and continue processing.
 6. This is not in the book. Define mutex, define semaphore, and explain the difference between them. 
Mutex class(ManualResetEventSlim) is a synchronization primitive that can also be used for interprocess synchronization. A semaphore class(SemaphoreSlim) limits the number of threads that can access a resource or pool of resources concurrently.
The difference between the Mutex class and the semaphore class is that the Mutex provides the functionality by which one or more tasks can wait for an event, while the semaphore class controls access to a pool of resources.  One is access while the other is functionality.
7. What does it mean to say that some collection classes are not thread safe? Explain how not being thread safe may lead one of these collection classes to produce a malfunction in the program.
 Thread safety is a technique which manipulates shared data structure in a manner that guarantees the safe execution of a piece of code by the multiple threads at the same time. A code is called thread safe if it is being called from multiple threads concurrently without the breaking of functionalities.  A collection class that is not thread safe does not support being called from multiple threads concurrently.
A collection class that is not thread safe can produce malfunctions in the program if it causes overlapping operation which can produce bugs in the process.
8. Explain how thread safe collection classes are made thread safe.
Collection classes are made thread safe by wrapping code that adds, queries, and removes elements in a collection.  So the .NET Framework class library includes a set of thread-safe collection classes and interfaces in the System.Collections.Concurrent namespace that are designed specifically for use with tasks.  
 9. Why are thread safe classes slower than non-thread safe classes? Be specific.
Thread safe classes are slower than non-thread safe classes because of the additional run-time overhead, so these classes are not as fast as the regular collection classes.

