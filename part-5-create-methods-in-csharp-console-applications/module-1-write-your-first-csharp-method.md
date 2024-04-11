# Write your first `C#` method

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/write-first-c-sharp-method/8-knowledge-check>

1. **Which of the following correctly declares a method?**

   - `DisplayNumbers();`
     > Incorrect. To declare a method, you need to include a return type.
   - `void DisplayNumbers{};`
     > Incorrect. Methods must use parentheses `()` after the name, and brackets `{}` to contain the method body.
   - `void DisplayNumbers() { }`
     > **Correct**. A method is declared using the return type, followed by parentheses `()` containing any parameters, and brackets `{}` to contain the method body.

2. **Which of the following correctly calls a method?**

   - `GenerateID();`
     > **Correct**! Methods are called using the name, followed by parentheses `()` and a semicolon.
   - `void GenerateID() {}`
     > Incorrect. To call a method, you must include parentheses `()` after the name, followed by a semicolon.
   - `GenerateID;`
     > Incorrect. To call a method, you must include parentheses `()` after the name, followed by a semicolon.

3. **Which of the following is true about the `return` keyword?**

   - `It's identical to the break keyword.`
     > Incorrect. The `break` keyword terminates a loop or switch statement, but the `return` keyword terminates the current method.
   - `It terminates the execution of a method.`
     > **Correct**! The `return` statement terminates execution of its method and returns control to the caller.
   - `It must always be used with a value or expression.`
     > Incorrect. `void` methods don't return values and can use the `return` keyword on its own.
