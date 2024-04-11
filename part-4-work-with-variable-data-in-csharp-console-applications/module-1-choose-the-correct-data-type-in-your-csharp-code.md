# Choose the correct data type in your `C#` code

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-choose-data-type/7-knowledge-check>

1. **A piece of code must store whole numeric values between negative and positive 1,000,000. Which is the best data type to be used?**

   - `float`
     > Incorrect. While `float` would work, its extra precision after the decimal doesn't fit the exact requirement of this scenario.
   - `double`
     > Incorrect. While `double` would work, its extra precision after the decimal doesn't fit the exact requirement of this scenario.
   - `int`
     > **Correct**. While `float` or `double` would work, their extra precision after the decimal doesn't fit the exact requirement of this scenario.

2. **The code for a game needs to store lots of fractional values representing x, y, and z positions in a large 3D space. It will likely need to perform physics calculations for trajectories and so on. Absolute precision isn't required, but it's important that the program runs as efficiently as possible. Which data type is best?**

   - `float`
     > **Correct**. Unlike `int`, `float` can store fractional numbers, and unlike `decimal`, `float` doesn't require extra memory to store extra precision that isn't needed in this scenario.
   - `decimal`
     > Incorrect. While `decimal` can store large fractional numbers, they require more memory to store all the precision. Furthermore, they're less efficient than `float` or `double`. Finally, they can return precise calculated values, but the question says that's not a priority in this situation.
   - `int`
     > Incorrect. `int` can't store fractional numbers.

3. **Which of the following statements is true?**

   - `Reference types are stored in the stack.`
     > Incorrect. Reference types are stored in the heap.
   - `Value types can only store numbers.`
     > Incorrect. While this module focused on integral and floating point data types, `char` is also a value type, and there are other non-numeric value types like `struct` and `enum`.
   - `Use the new operator to create a new instance of a reference type and return its address to the variable.`
     > **Correct**. Use the `new` operator to create a new instance of a reference type and return its address to the variable.
