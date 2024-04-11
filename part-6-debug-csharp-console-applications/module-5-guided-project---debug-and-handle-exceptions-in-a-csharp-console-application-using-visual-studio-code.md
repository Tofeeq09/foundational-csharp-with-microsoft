# Guided project - Debug and handle exceptions in a `C#` console application using Visual Studio Code

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/guided-project-debug-handle-exceptions-c-sharp-console-application/5-knowledge-check>

1. **What is the purpose of catching an exception in C#?**

   - `To ignore the errors that occur in a program.`
     > Incorrect. Exceptions should be handled in code to correct error conditions if possible.
   - `To generate other exceptions in a program.`
     > Incorrect. Exceptions can be thrown when an issue or error is detected, but the catch clause isn't a tool for generating errors.
   - `To take corrective action when an error occurs in a program.`
     > **Correct**. The purpose of catching an exception is to take corrective action when an error occurs.

2. **What is the relationship between the type of exception and the information it contains?**

   - `The type of exception and the information it contains are unrelated.`
     > Incorrect. Properties of the exception object contain information related to the exception type.
   - `The type of exception determines the information it contains.`
     > **Correct**. The type of exception determines the information it contains.
   - `The information contained in an exception determines the type of exception.`
     > Incorrect. The exception type determines what information the exception contains, not the other way around.

3. **What is a conditional breakpoint in Visual Studio Code?**

   - `A breakpoint that only triggers when a specified condition is met.`
     > **Correct**. A conditional breakpoint is a special type of breakpoint that only triggers when a specified condition is met.
   - `A breakpoint that is triggered every time the code is run.`
     > Incorrect. A conditional breakpoint is triggered when a specified condition is met.
   - `A breakpoint that is only visible in the editor and doesn't affect debugging.`
     > Incorrect. A conditional breakpoint affects debugging and pauses execution when the condition is met.

4. **When is an ArgumentOutOfRangeException exception thrown?**

   - `An ArgumentOutOfRangeException exception is thrown when an attempt is made to index an array outside the bounds of the array.`
     > Incorrect. This answer choice describes when an IndexOutOfRangeException exception is thrown.
   - `An ArgumentOutOfRangeException exception is thrown when the value of an argument is outside the allowable range of values as defined by the method.`
     > **Correct**. An ArgumentOutOfRangeException exception should only be thrown when the value of an argument is outside the allowable range of values as defined by the invoked method.
   - `An ArgumentOutOfRangeException exception is thrown when an attempt is made to store a value of one type in an array of another type.`
     > Incorrect. This answer choice describes when a ArrayTypeMismatchException exception is thrown.

5. **What is the recommended approach for catching exceptions in C#?**

   - `Catch any type of exception without specifying an object argument.`
     > Incorrect. Catching any type of exception without specifying an object argument isn't recommended.
   - `Catch only the exceptions that your code knows how to recover from.`
     > **Correct**. The recommended approach is to catch only the exceptions that your code knows how to recover from.
   - `Catch only the exceptions that aren't derived from System.Exception.`
     > Incorrect. All exceptions in C# are derived from System.Exception.
