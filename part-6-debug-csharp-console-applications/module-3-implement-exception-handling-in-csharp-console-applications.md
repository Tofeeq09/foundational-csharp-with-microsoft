# Implement exception handling in `C#` console applications

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/implement-exception-handling-c-sharp/10-knowledge-check>

1. **What does the try code block contain?**

   - `The code that cleans up resources and is executed whether an exception occurs or not.`
     > Incorrect. The finally code block contains the code that cleans up resources and is executed whether an exception occurs or not.
   - `The code that throws an exception object.`
     > Incorrect. The try code block isn't used to throw an exception object.
   - `The code that may cause an exception.`
     > **Correct**. The try code block contains the guarded code that may cause an exception.

2. **What is the purpose of the catch code block?**

   - `To clean up any resources that are allocated in a try block.`
     > Incorrect. The catch code block isn't used to clean up resources.
   - `To handle the exception, log it, or ignore it.`
     > **Correct**. The catch code block contains the code that's executed when an exception is caught. The catch block can handle the exception, log it, or ignore it.
   - `To execute code that may cause an exception.`
     > Incorrect. The catch code block isn't used to execute code that may cause an exception.

3. **When is an IndexOutOfRangeException exception thrown?**

   - `An IndexOutOfRangeException exception is thrown when an attempt is made to store a value of one type in an array of another type.`
     > Incorrect. This answer choice describes when a ArrayTypeMismatchException exception is thrown.
   - `An IndexOutOfRangeException exception is thrown when attempting an invalid casting or explicit conversion.`
     > Incorrect. This answer choice describes when a InvalidCastException exception is thrown.
   - `An IndexOutOfRangeException exception is thrown when an attempt is made to index an array outside the bounds of the array.`
     > **Correct**. An IndexOutOfRangeException exception is thrown when an attempt is made to access an element of an array or collection with an index that is outside its bounds.

4. **When is an ArrayTypeMismatchException exception thrown?**

   - `An ArrayTypeMismatchException exception is thrown when an attempt is made to store a value of one type in an array of another type.`
     > **Correct**. The ArrayTypeMismatchException exception is thrown when an attempt is made to store an element of the wrong type within an array.
   - `An ArrayTypeMismatchException exception is thrown when attempting to access a member on a type whose value is null.`
     > Incorrect. This answer choice describes when a NullReferenceException exception is thrown.
   - `An ArrayTypeMismatchException exception is thrown when an attempt is made to index an array outside the bounds of the array.`
     > Incorrect. This answer choice describes when a IndexOutOfRangeException exception is thrown.

5. **What is the name of the base class that all derived exception types inherit from?**

   - `Object.`
     > Incorrect. Object isn't an exception type.
   - `System.`
     > Incorrect. System isn't an exception type.
   - `Exception.`
     > **Correct**. In C#, System.Exception is the base class that all derived exception types inherit from.

6. **Which property of an exception object can be used to determine where an error occurred?**

   - `InnerException.`
     > Incorrect. The InnerException property can be used to create and preserve a series of exceptions during exception handling.
   - `StackTrace.`
     > **Correct**. The StackTrace property contains a stack trace that can be used to determine where an error occurred.
   - `TargetSite.`
     > Incorrect. The TargetSite property can be used to get the method that throws the current exception.

7. **What is the recommended approach for catching exceptions in C#?**

   - `Catch any type of exception without specifying an object argument.`
     > Incorrect. Catching any type of exception without specifying an object argument isn't recommended.
   - `Catch only the exceptions that your code knows how to recover from.`
     > **Correct**. The recommended approach is to catch only the exceptions that your code knows how to recover from.
   - `Catch only the exceptions that are not derived from System.Exception.`
     > Incorrect. All exceptions in C# are derived from System.Exception.

8. **What is the name of the specific exception type that occurs when attempting to divide by zero in C#?**

   - `ArithmeticException.`
     > Incorrect. The ArithmeticException exception type is a base class for exceptions that occur in arithmetic operations.
   - `InvalidCastException.`
     > Incorrect. The InvalidCastException exception type is thrown when an explicit conversion from one data type to another fails.
   - `DivideByZeroException.`
     > **Correct**. In C#, the specific exception type that occurs when attempting to divide by zero is DivideByZeroException.
