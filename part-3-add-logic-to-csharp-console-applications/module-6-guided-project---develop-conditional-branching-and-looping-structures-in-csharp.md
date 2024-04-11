# Guided project - Develop conditional branching and looping structures in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/guided-project-develop-conditional-branching-looping/7-knowledge-check>

1. **When is it appropriate to use a switch-case construct rather than a if-elseif-else construct?**

   - `A switch-case construct is appropriate when more than 2-3 else if code blocks are required.`
     > **Correct**! When more than 2-3 else if code blocks are required, the code can become difficult to read, and the switch-case construct is preferable.
   - `A switch-case construct is appropriate when the number of case patterns is small.`
     > Incorrect. If fewer than 2-3 case patterns are included in the selection list of a switch statement, an if-elseif-else construct may be the better choice.
   - `A switch-case construct is appropriate when the selection statement is inside a loop.`
     > Incorrect. Being inside a loop doesn't affect the choice between a switch-case construct and a if-elseif-else construct.

2. **Why should a developer choose a `for` statement rather than a `foreach` statement when processing the contents of a multidimensional array?**

   - `for statements do a better job of examining each array item separately.`
     > Incorrect. A `foreach` statement processes each array item separately.
   - `foreach statements do a better job of examining each array item separately.`
     > Incorrect. It's true that a `foreach` statement processes each array item separately. However, that is a reason to choose a `foreach` statement, not a reason to choose a `for` statement.
   - `for statements enable a developer to treat array dimensions separately.`
     > **Correct**! When their code is processing the contents of a multidimensional array, a developer often wants to iterate through the array dimensions separately. The `for` statement provides better support for processing array dimensions separately.

3. **Why is it important to scope a variable at its lowest necessary level?**

   - `It ensures that a variable that's declared outside of a code block, can be accessed inside the code block before it's been assigned a value.`
     > Incorrect. A variable that's declared outside a code block must be assigned a value before it can be accessed inside the code block. If the variable hasn't been initialized a build error occurs.
   - `It ensures that application resources and the security footprint are kept small.`
     > **Correct**. Keeping variables scoped at the lowest necessary level enables better resource management and helps to minimize the attack profile of the application.
   - `It ensures that a variable can be accessed within the lowest level code branches of an application.`
     > Incorrect. Scoping a variable at its lowest necessary level doesn't ensure the variable is accessible within all low level code branches of an application.
