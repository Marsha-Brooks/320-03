
C# Discussion Questions
Chapter 23 Lesson plan 1/2nd Term

1. List two reasons for multitasking, and explain the rationale for them. 
Two reasons to improve multitasking are:
A) To improve responsiveness
	  Tasks that do not require runtime or processor time that can be conducted without wasting
CPU cycle and program can continue on without halting to respond to other tasks, like user input.
B) To improve scalability
	Design that runs parallel tasks concurrently that are CPU bound.  Parallelize tasks to monopolize resources.

2. Explain Moore’s law. What does Moore’s law have to do with multitasking?
Gordon E. Moore, cofounder of intel, wrote that the number of resistors that can be placed inexpensively on an integrated circuit will increase exponentially doubling approximately every two years. 
Moore’s Law relates to multitasking in that as he projected technology advanced with data being passed faster, and after the evolution of the 3GHZ processor - multicore processors evolved making computers even more capable of handling advanced multitasking processes effortlessly and inexpensively.

 3. In UWP, what namespace is used as the container for the multitasking methods?
The Task Class  is the namespace that is used as the container for the multitasking methods.

 4. What is the difference between tasks and threads? Explain. 
The difference between a task and a thread is, a task is an object created to run a block of code while a thread object is created to execute and schedule those tasks objects that are created. 

5. What is the Thread Pool?
A thread pool is a class that implements a number of optimizations and uses a work-stealing algorithm to ensure that threads are scheduled efficiently.  Implemented by a ThreadPool object. It is part of a queue for organizing and implementing concurrent tasks and multiple threads.
 6. What parameters does the Task () constructor take?
A Task () constructor takes an Action delegate as a parameter, that references a method that does not return a value.  A task object invokes this delegate when it is scheduled to run.  

 7. How do you start a thread? 
When you create a task object, the WinRT creates the appropriate thread and schedules and executes your task according to the available processor.  So you do not start a thread, you create a task and the WinRT automatically starts a thread in response.

8. What is the difference between the Start () and Run() methods?
The Start() method is used to start a task running explicitly
The Run() method is used to start a task immediately returning a reference to the task object

 9. What is the difference between creating independent tasks with Tasks and parallelization with Parallel? Explain.
The difference between creating independent tasks and parallelizing tasks is that an independent task is just what it states.  It is a task that runs independently from other tasks or nonconcurrent, monopolizing control of the processor until the task completes, while a parallelized task runs concurrently with other tasks set to run concurrently or in parallel with it.
Parallelized tasks are managed by a queue with the use of the Thread class and a Thread Pool, run when processor space and resources are available. If multitasking or parallelization is not utilized, the application will run like on a single-core processor regardless of the cores available.

 10. Explain how manual cancellation works using a cancellation token.
When cancelling manually using a cancellation token, you must set the Boolean value of the IsCancellationRequested property to “True”.
