# Add looping logic to your code using the do-while and while statements in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-do-while/7-knowledge-check>

1. **A developer needs to iterate through an array of items. The number of items in the array is unknown. The code inside the iteration code block examines each item sequentially to select an item that matches specified criteria. The index number of the selected array element isn't important. The selected item is referenced multiple times within the code block. Which type of iteration statement is best suited for this scenario?**

   - `foreach`
     > **Correct**! It's possible to use any of these iteration types for the conditions described, but a `foreach` is best suited for this scenario. The `foreach` is easy to implement when the number of array elements is unknown. The `foreach` is a good choice when the index number of the selected array element isn't important. The `foreach` might run faster when the selected item is used multiple times within the code block.
   - `for`
     > Incorrect. It's possible to use the `for` statement, but it isn't the best choice for this scenario.
   - `while`
     > Incorrect. It's possible to use the `while` statement, but it isn't the best choice for this scenario.

2. **A developer needs to capture a list of items from the user. The user will enter the keyboard combination ctrl + Esc to exit. Which is the best iteration statement for this purpose?**

   - `foreach`
     > Incorrect. It's remotely possible to use the `foreach` statement for this purpose, but it wouldn't be straight forward.
   - `do-while`
     > **Correct**! The `do-while` will allow the code to check each entry by the user until they enter the special keyboard combination to exit.
   - `while`
     > Incorrect. It's possible to use the `while` statement, but the `do-while` will allow the user to enter a value before the code begins checking for the special keyboard combination.
