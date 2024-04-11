# Create `C#` methods that return values

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/create-c-sharp-methods-return-values/9-knowledge-check>

1. **Which of the following options correctly returns a string value?**

   - `return "";`
     > **Correct**! An empty string is a valid string result.
   - `return 'a';`
     > Incorrect. This code attempts an implicit conversion from `char` to `string` that isn't allowed.
   - `return 5;`
     > Incorrect. This code attempts an implicit conversion from `int` to `string` that isn't allowed.

2. **Which of the following statements is true about the `return` keyword?**

   - `It starts a new iteration of a method.`
     > Incorrect. The `continue` statement starts a new iteration of a loop.
   - `It terminates the execution of a method.`
     > **Correct**! The `return` statement terminates execution of its method and returns control to the caller.
   - `It must always be used with a value or expression.`
     > Incorrect. `void` methods don't return values and can use the `return` keyword on its own.

3. **Which of the following options is a valid return statement?**

   - `return void;`
     > Incorrect. `void` isn't a valid return value.
   - `return 5 % 2;`
     > **Correct**! This statement would return the value of the expression `5 % 2`.
   - `return Console.WriteLine();`
     > Incorrect. `Console.WriteLine()` is a `void` method and can't be used in a return statement.
