# Branch the flow of code using the switch-case construct in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-switch-case/5-knowledge-check>

1. **What is the purpose of a default case in a switch statement?**

   - `It's used to specify the condition for the switch statement.`
     > Incorrect. The default case is not used to specify the condition for the switch statement.
   - `It's used to end the switch statement.`
     > Incorrect. The default case doesn't end the switch statement.
   - `It's used to execute a block of code if no case matches the expression.`
     > **Correct**! The default case executes when no other case matches the switch expression.

2. **What happens if a break statement (or alternative keyword that prevents "fall-through") is omitted in a switch case?**

   - `The default case will execute.`
     > Incorrect. The default case won't execute if a break statement is omitted.
   - `The impacted case sections will be removed by the compiler.`
     > Incorrect. The compiler doesn't remove case sections that allow “fall through” to the next switch section.
   - `The compiler will generate an error.`
     > **Correct**! Only one switch section is allowed to be executed. If you forget the break keyword (or, optionally, the return keyword) the compiler will generate an error.
