# Evaluate Boolean expressions to make decisions in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-evaluate-boolean-expressions/8-knowledge-check>

1. **Which line of code uses logical negation?**

   - `Console.WriteLine(!value);`
     > **Correct**! Adding the `!` operator (the "not-operator") before a conditional expression forces your code to reverse its evaluation of the operand. When logical negation is applied, the evaluation produces `true` if the operand evaluates to `false` and `false` if the operand evaluates to `true`.
   - `Console.WriteLine(value != false);`
     > Incorrect. Using the inequality operator to evaluate whether `value` isn't equal to `false` isn't an example of logical negation.
   - `Console.WriteLine(a != b);`
     > Incorrect. Using the inequality operator to evaluate whether two values aren't equal isn't an example of logical negation.

2. **Which of the following lines of code is a valid use of the conditional operator?**

   - `int value = amount >= 10 ? 10 : 20;`
     > **Correct**! The syntax for a conditional operator is `? (value 1) : (value 2)`.
   - `int value = amount >= 10 : 10 ? 20;`
     > Incorrect. The conditional operator is reversed.
   - `int value = amount >= 10 ? 10 | 20;`
     > Incorrect. The pipe character isn't a component of the conditional operator syntax.
