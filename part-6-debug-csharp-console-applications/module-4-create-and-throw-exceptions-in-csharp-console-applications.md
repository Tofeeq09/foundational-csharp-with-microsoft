# Create and throw exceptions in `C#` console applications

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/create-throw-exceptions-c-sharp/6-knowledge-check>

1. **A developer needs to create and throw an exception in a C# application. Which of the following descriptions is correct?**

   - `The exception type shouldn't match the intended purpose of the exception.`
     > Incorrect. The exception type should match the intended purpose of the exception.
   - `The exception type that they create depends on the coding issue.`
     > **Correct**. The exception type created depends on the coding issue and should match the intended purpose of the exception as closely as possible.
   - `The process for throwing an exception object involves using the catch keyword.`
     > Incorrect. The process for throwing an exception object involves using the throw keyword, not the catch keyword.

2. **When should a method throw an exception?**

   - `A method should throw an exception when the method can complete its intended purpose.`
     > Incorrect. Methods should only throw an exception when an issue or error is detected that prevents them from completing their intended purpose.
   - `A method should throw an exception when the method can't complete its intended purpose.`
     > **Correct**. Methods should throw an exception whenever they can't complete their intended purpose.
   - `A method should throw an exception when an exception type matches the intended purpose of the method.`
     > Incorrect. Methods should only throw an exception when an issue or error is detected that prevents them from completing their intended purpose.

3. **A developer needs to create an exception object that includes a specific Message property. Which of the following statements is correct?**

   - `The Message property of an exception is writable.`
     > Incorrect. The Message property is a read-only property. It can only be assigned when instantiating the exception object.
   - `The Message property shouldn't explain the reason for the exception.`
     > Incorrect. The Message property of an exception should explain the reason for the exception.
   - `The Message property should explain the reason for the exception.`
     > **Correct**. The Message property of an exception should explain the reason for the exception. Since Message is a read-only property, it must be assigned when instantiating the exception object.
