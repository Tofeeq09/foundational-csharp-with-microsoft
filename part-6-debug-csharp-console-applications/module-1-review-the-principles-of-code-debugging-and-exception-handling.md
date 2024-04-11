# Review the principles of code debugging and exception handling

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/review-principles-code-debugging-exception-handling-c-sharp/5-knowledge-check>

1. **What is code debugging?**

   - `A process to identify code syntax errors during the build process.`
     > Incorrect. Syntax issues are normally exposed by IntelliSense and corrected before running the application.
   - `A process to isolate and fix issues in code logic.`
     > **Correct**. Code debugging involves isolating and fixing logic issues in code.
   - `A process to verify that code builds and runs without errors.`
     > Incorrect. Developers debug code that runs without errors. For example, when the application includes logic issues.

2. **What is a debugger?**

   - `A software tool used to observe and control the execution flow of a program.`
     > **Correct**. A debugger is a software tool uses an analytical approach to observe and control the execution flow of a program.
   - `A program that generates code automatically based on user input.`
     > Incorrect. Debuggers are used isolate logic issues in an application. They are not used to generate code.
   - `A tool that helps developers write their code faster.`
     > Incorrect. Although code debuggers speed the debugging process and help to identify issues, they do not help with writing code.

3. **What happens when execution of a C# application results in a system error?**

   - `The program crashes and closes.`
     > Incorrect. An exception is thrown when a system error occurs. If the exception is caught and handled, execution continues normally.
   - `The .NET runtime creates and throws an exception.`
     > **Correct**. The .NET runtime throws an exception when a C# application generates a system error.
   - `The error is silently ignored and the program continues to run.`
     > Incorrect. The .NET runtime throws an exception and the application is shut down if the exception isn't caught.

4. **What is the purpose of catching an exception in C#?**

   - `To ignore the errors that occur in a program.`
     > Incorrect. Exceptions should be handled in code to correct error conditions if possible.
   - `To generate other exceptions in a program.`
     > Incorrect. Exceptions can be thrown when an issue or error is detected, but the catch clause is not a tool for generating errors.
   - `To take corrective action when an error occurs in a program.`
     > **Correct**. The purpose of catching an exception is to take corrective action when an error occurs.

5. **What is the relationship between the type of exception and the information it contains?**

   - `The type of exception determines the information it contains.`
     > **Correct**. The type of exception determines the information it contains.
   - `The type of exception and the information it contains are unrelated.`
     > Incorrect. Properties of the exception object contain information related to the exception type.
   - `The information contained in an exception determines the type of exception.`
     > Incorrect. The exception type determines what information the exception contains, not the other way around.
