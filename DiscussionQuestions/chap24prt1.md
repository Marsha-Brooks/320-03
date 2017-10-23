
C# Chapter 24 (559-575) Discussion Questions.
Asynchronicity
1. What is an asynchronous method? When the book talks about a contract, what is the contract and who is it with?
An asynchronous method is a method that uses a background thread for operations that could cause delay.  The method returns control of the current thread to the calling environment as quickly as possible, this action is based on a “contract” with the calling environment.  The contract is implied and it is with the caller, the Task Object. 
2. What can be the problem with decomposing a series of discrete method calls into a set of tasks, such as we saw in chapter 23?
 The problem with decomposing a series of discrete method calls into a set of tasks, is that the tasks must be run often in a serialized way that if you do not apply the async keyword and the await operator correctly; you could very easily end up in a deadlock. You must define a continuation to prevent stalling out.

3. What can be the problem with decomposing a series of discrete method calls into a set of continuations? When does the last continuation “complete” as compared to the previous continuations? What problem might this cause?
The problem with decomposing a series of discrete method calls into a set of continuations is that with the use of the start method..it initiates the Task, it does not wait for it to complete, so processes can get out of order, waiting for tasks to complete., the use of the Wait method Is necessary.
4. What might be the problem with implementing the previous solution as a continuation passing a delegate? What would be your interpretation with this error message: “The application called an interface that was marshaled for a diﬀerent thread.”?
The problem with implementing the solution only the user interface thread can manipulate user interface controls and by using this solution, you are attempting to write to a control from a different thread, the one being used for the task; causing an exception to be thrown. “The application called an interface that was marshalled for a different thread”
5. The book suggests a solution using a continuation delegate calling another continuation delegate via an async function. What does the book identify as a problem with this suggested solution?
The book defines the problem as: only the user interface thread can manipulate user interface controls and by using this solution, you are attempting to write to a control from a different thread, the one being used for the task; causing an exception to be thrown. In addition, once you use this solution; the compiler determines a return value.  You can no longer specify a return value yourself, your code will not compile.
6. What does the async modiﬁer do? What does the await operator do?
The asynch modifier tells the compiler that the method contains functionality that can be run asynchronously.  The await operator specifies a point at which the compiler can split the code into a continuation.

7. What is an awaitable object? Be speciﬁc.
An awaitable object is a type that provides the GetAwaiter method, which returns an object that in turn provides methods for funning code and awaiting or it to complete. Such as a Task Object.

8. In a method deﬁnition, how do you create and run a Task and return a reference to the Task? What is the type of such a method? What does the method return?
In a method definition, the way you create and run a task and return a reference to a task is by using the async keyword and using the run and start methods of the Task Objects .  The compiler refactors your code and returns a reference to the task.

9. How do you deﬁne method calls in the implementation of an async method? Speciﬁcally, you must deﬁne a task, you must run the task, you must implement the task, and you must await the task. What is the syntax for doing this?
To define method calls in the implementation of an async method, you use the async modifier that contains the functionality that can be run asynchronously and the await operator that specifies the points at which this asynchronous functionality should be performed.  The syntax is resembled below:

Private async void slowMethod()
{
await doFirstLongRunningOperation();
await doSecondRunningOperation();
await doThirdRunningOperation();
Message.Text  = “Processing Complete”;

}

10. What is the diﬀerence between decomposing a series of method calls that do not return values, and a series of method calls that return values? What is the Result property of a method that returns a value? How do you use the await operator in this circumstance?
The difference between running an asynchronous method that is void versus an asynchronous method that returns a value is the use of the Task<TResult>  type.  The return property of a async method that returns a value is the Task<TResult> type, while a void async method simply returns a task.   The await operator extracts the value for the Task returned by the asynchronous method and assigns it to the result variable.

11. What is the diﬀerence between the await operator and the Wait method?
The difference between the await operator and the wait method is that the wait method always blocks the current thread and does not allow it to be used until the task completes, while the await operator attempts to obtain the original thread that was used to invoke the asynchronous method call.  With the await method, if the thread is busy the code will be blocked.
