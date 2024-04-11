# Challenge project - Develop branching and looping structures in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/challenge-project-develop-branching-looping-structures-c-sharp/5-knowledge-check>

1. **A developer is writing an application in Visual Studio Code. They save changes to their Program.cs file, and then run the `dotnet build` command in the Terminal panel. What information can they find in reported Error and Warning messages?**

   - `One or more suggestions for how to fix any syntax issues detected.`
     > Incorrect. Error and Warning messages don't include suggested fixes.
   - `The line number and information about what caused the error.`
     > **Correct**. Error and Warning messages include a description of the issue and the line number where it occurs.
   - `Links to help documentation.`
     > Incorrect. Error and Warning messages don't include links to documentation.

2. **A developer needs to create an iteration statement. Under what condition is a `while` statement a better choice than a `do` statement?**

   - `When the expression values evaluated by the iteration statement are unknown prior to the iteration code block.`
     > Incorrect. A `do` statement would work well in this situation.
   - `When the expression values evaluated by the iteration statement are known prior to the iteration code block.`
     > **Correct**. When the code is able to evaluate the loop expression prior to the loop, a `while` statement allows the code to implement zero iterations.
   - `When the developer creates nested do or while loops.`
     > Incorrect. Nesting loops isn't a factor in this decision.
