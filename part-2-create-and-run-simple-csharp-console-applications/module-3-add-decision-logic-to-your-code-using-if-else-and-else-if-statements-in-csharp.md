# Add decision logic to your code using `if`, `else`, and `else if` statements in `C#`

## Introduction

The **C# programming language** allows you to build applications that employ **decision-making logic**.

Suppose you want to display different information to the end user depending on some business rules. For example, what if you want to display a special message on a customer's bill based on their geographic region? What if you want to give a customer a discount based on the size of their order? Or what if you want to display an employee's title based on their level in the company. In each case, you would need to add **decision logic**.

## Create decision logic with if statements

Most applications include a large number of **execution paths**. For example, an application could implement different execution paths based on which menu option a user selects. Developers refer to the code that implements different execution paths as **code branches**.

The most widely used code branching statement is the **if statement**. The if statement relies on a **Boolean expression** that is enclosed in a set of parentheses. If the expression is true, the code after the if statement is executed. If not, the .NET runtime ignores the code and doesn't execute it.

In this exercise, you'll practice writing if statements by creating a game. First you'll define the rules of the game, then you'll implement them in code.

You'll use the **Random.Next()** method to simulate rolling three six-sided dice. You'll evaluate the rolled values to calculate the score. If the score is greater than an arbitrary total, then you'll display a winning message to the user. If the score is below the cutoff, you'll display a losing message to the user.

- If any two dice you roll result in the same value, you get two bonus points for rolling **doubles**.
- If all three dice you roll result in the same value, you get six bonus points for rolling **triples**.
- If the sum of the three dice rolls, plus any point bonuses, is 15 or greater, you **win the game**. Otherwise, you **lose**.

### Write code that generates three random numbers and displays them in output

```csharp
Random dice = new Random();

int roll1 = dice.Next(1, 7);
int roll2 = dice.Next(1, 7);
int roll3 = dice.Next(1, 7);

int total = roll1 + roll2 + roll3;

Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}"); // Output: Dice roll: 3 + 6 + 1 = 10

```

To begin, you create a new instance of the **System.Random** class and store a reference to the object in a variable named `dice`. Then, you call the **Random.Next()** method on the `dice` object three times, providing both the lower and upper bounds to restrict the possible values between 1 and 6 (the upper bound is exclusive). You save the three random numbers in the variables `roll1`, `roll2`, and `roll3`, respectively.

Next, you sum the three dice rolls and save the value into an integer variable named `total`.

Finally, you use the **WriteLine()** method to display the three values using **string interpolation**.

### Add an if statement to display different messages based on the value of the total variable

```csharp
if (total > 14)
{
    Console.WriteLine("You win!");
}

if (total < 15)
{
    Console.WriteLine("Sorry, you lose.");
}
```

These two **if statements** are used to handle the winning and losing scenarios. Take a minute to examine the first if statement.

Notice that the if statement is made up of three parts:

1. The **if keyword**
2. A **Boolean expression** between parenthesis `()`
3. A **code block** defined by curly braces `{ }`

At run time, the Boolean expression `total > 14` is evaluated. If this is a true statement (if the value of `total` is greater than 14) then the flow of execution will continue into the code defined in the code block. In other words, it will execute the code in the curly braces.

However, if the Boolean expression is false (the value of `total` not greater than 14) then the flow of execution will skip past the code block. In other words, it will not execute the code in the curly braces.

Finally, the second if statement controls the message if the user loses. In the next unit, you'll use a variation on the if statement to shorten these two statements into a single statement that more clearly expresses the intent.

### What is a Boolean expression?

A **Boolean expression** is a piece of code that evaluates to a Boolean value: either `true` or `false`. The most straightforward Boolean expressions are the literal values `true` and `false`. However, a Boolean expression can also be the outcome of a method that returns a Boolean value. For instance, the **string.Contains()** method can be used to determine if a specific string contains another string, returning `true` if it does and `false` otherwise.

```csharp
string message = "The quick brown fox jumps over the lazy dog.";
bool result = message.Contains("dog");
Console.WriteLine(result);

if (message.Contains("fox"))
{
    Console.WriteLine("What does the fox say?");
}
```

Since `message.Contains("fox")` returns a Boolean value (`true` or `false`), it qualifies as a **Boolean expression** and can be used in an `if` statement.

You can also create simple Boolean expressions by using **comparison operators** to compare two values. These operators include:

- `==`, the **equality operator**, tests if two values are equal.
- `!=`, the **inequality operator**, tests if two values are not equal.
- `>`, the **greater than operator**, checks if the value on the left is greater than the value on the right.
- `<`, the **less than operator**, checks if the value on the left is less than the value on the right.
- `>=`, the **greater than or equal to operator**, checks if the value on the left is greater than or equal to the value on the right.
- `<=`, the **less than or equal to operator**, checks if the value on the left is less than or equal to the value on the right.

In this example, you evaluated the Boolean expression `total > 14`. However, you could have chosen the Boolean expression `total >= 15` because in this case, they're the same. Given that the rules to the game specify "If the sum of the three dice, plus any bonuses, is 15 or greater, you win the game", you should probably implement the `>= 15` expression. You'll make that change in the next step of the exercise.

### What is a code block?

A **code block** is a collection of one or more lines of code that are defined by an opening and closing curly brace symbol `{ }`. It represents a complete unit of code that has a single purpose in your software system. In this case, at runtime, all lines of code in the code block are executed if the Boolean expression is `true`. Conversely, if the Boolean expression is `false`, all lines of code in the code block are ignored.

It's important to note that code blocks can contain other code blocks. In fact, it's common for one code block to be "nested" inside another code block in your applications. You'll begin nesting your own code blocks later in this module when you create one `if` statement inside the code block of another.

### Add another if statement to implement the doubles bonus

Next, you can implement the rule: "If any two dice you roll result in the same value, you get two bonus points for rolling **doubles**" and "If all three dice you roll result in the same value, you get six bonus points for rolling **triples**."

In programming, logical operators are used to combine multiple conditions. In C#, the primary logical operators are `&&` (AND), `||` (OR), and `!` (NOT). Here's a brief explanation of each:

The `&&` operator, also known as the **logical AND operator**, is used to combine two Boolean expressions. It returns `true` only if both expressions evaluate to `true`. If either or both expressions are `false`, the `&&` operator returns `false`.

The `||` operator, also known as the **logical OR operator**, is used to combine two Boolean expressions. It returns `true` if either (or both) of the expressions evaluate to `true`. If both expressions are `false`, the `||` operator returns `false`.

The `!` operator, also known as the **logical NOT operator**, is used to reverse the Boolean value of an expression. It returns `true` if the expression is `false` and `false` if the expression is `true`.

```csharp
Random dice = new Random();

int roll1 = dice.Next(1, 7);
int roll2 = dice.Next(1, 7);
int roll3 = dice.Next(1, 7);

int total = roll1 + roll2 + roll3;

Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");

if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3))
{
    Console.WriteLine("You rolled doubles! +2 bonus to total!");
    total += 2;
}

if ((roll1 == roll2) && (roll2 == roll3)) 
{
    Console.WriteLine("You rolled triples! +6 bonus to total!");
    total += 6;
}

if (total >= 15)
{
    Console.WriteLine("You win!");
}

if (total < 15)
{
    Console.WriteLine("Sorry, you lose.");
}
```

But wait, should you really reward the player with both the **triple bonus** and the **double bonus**? After all, a roll of triples implies that they also rolled doubles. Ideally, the bonuses shouldn't stack. There should be two separate bonus conditions. This is a **bug in logic** that will need to be corrected.

### Check your knowledge - 1

1. **What is a code block?**

   - A .NET Class Library.
    > Incorrect. Although it's true that reference material on classes and methods is found in the .NET Class Library, this answer isn't complete.

   - Lines of code that should be treated as a single unit.
    > Correct! A code block is defined by curly braces `{ }`. It collects lines of code that should be treated as a single unit.

   - A block of code that is blocked from being accessed.
    > Incorrect. A code block isn't a block of code that is blocked.

2. **What is a Boolean statement or expression?**

   - A modulus expression.
    > Incorrect. A Boolean expression isn't a modulus expression.

   - An ordinal term.
    > Incorrect. A Boolean expression isn't an ordinal term.

   - Code that returns either true or false.
    > Correct! A Boolean expression is any code that returns a Boolean value, either true or false.

## Create nested decision logic with if, else if, and else

### Use if and else statements instead of two separate if statements

```csharp
Random dice = new Random();

int roll1 = dice.Next(1, 7);
int roll2 = dice.Next(1, 7);
int roll3 = dice.Next(1, 7);

int total = roll1 + roll2 + roll3;

Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");

if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3))
{
    Console.WriteLine("You rolled doubles! +2 bonus to total!");
    total += 2;
}

if ((roll1 == roll2) && (roll2 == roll3)) 
{
    Console.WriteLine("You rolled triples! +6 bonus to total!");
    total += 6;
}

if (total >= 15)
{
    Console.WriteLine("You win!");
}

if (total < 15)
{
    Console.WriteLine("Sorry, you lose.");
}
```

Becomes:

```csharp
Random dice = new Random();

int roll1 = dice.Next(1, 7);
int roll2 = dice.Next(1, 7);
int roll3 = dice.Next(1, 7);

int total = roll1 + roll2 + roll3;

Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");

if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3))
{
    Console.WriteLine("You rolled doubles!  +2 bonus to total!");
    total += 2;
}

if ((roll1 == roll2) && (roll2 == roll3))
{
    Console.WriteLine("You rolled triples!  +6 bonus to total!");
    total += 6;
}

if (total >= 15)
{
    Console.WriteLine("You win!");
}
else 
{
    Console.WriteLine("Sorry, you lose.");
}
```

### Modify the code to remove the stacking bonus for doubles and triples using nesting

**Nesting** allows you to place code blocks inside of code blocks. In this case, you'll nest an `if` and `else` combination (the check for doubles) inside of another `if` statement (the check for triples) to prevent both bonuses from being awarded.

```csharp
Random dice = new Random();

int roll1 = dice.Next(1, 7);
int roll2 = dice.Next(1, 7);
int roll3 = dice.Next(1, 7);

int total = roll1 + roll2 + roll3;

Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");

if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3))
{
    if ((roll1 == roll2) && (roll2 == roll3))
    {
        Console.WriteLine("You rolled triples!  +6 bonus to total!");
        total += 6;
    }
    else
    {
        Console.WriteLine("You rolled doubles!  +2 bonus to total!");
        total += 2;
    }
}

if (total >= 15)
{
    Console.WriteLine("You win!");
}
else 
{
    Console.WriteLine("Sorry, you lose.");
}
```

The goal is to create an inner `if-else` construct where the two outcomes are related opposites, and then use the opposing outcomes (`if/true` and `else/false`) to award the bonus points for triples and doubles. To achieve this goal, you check for doubles in the outer `if` statement, and then for triples in the inner `if` statement. This pattern ensures that when the inner check for triples returns `false`, your `else` code block can award the points for doubles.

Coming up, you will "**hard code**" the results of your three rolls in order to test your code logic.

To test for a roll of doubles, enter the following code:

```csharp
// int roll1 = dice.Next(1, 7);
// int roll2 = dice.Next(1, 7);
// int roll3 = dice.Next(1, 7);

int roll1 = 6;
int roll2 = 6;
int roll3 = 5;

// Rest of the code remains the same

/* Output:
Dice roll: 6 + 6 + 5 = 17
You rolled doubles!  +2 bonus to total!
You win!
*/
```

To test for a roll of triples, enter the following code:

```csharp
// int roll1 = dice.Next(1, 7);
// int roll2 = dice.Next(1, 7);
// int roll3 = dice.Next(1, 7);

int roll1 = 6;
int roll2 = 6;
int roll3 = 6;

// Rest of the code remains the same

/* Output:
Dice roll: 6 + 6 + 6 = 18
You rolled triples!  +6 bonus to total!
You win!
*/
```

If both work then you can be confident that your code is functioning as expected and remove the hard-coded values and use the `Random.Next()` method to generate random values like before.

### Use if, else, and else if statements to give a prize instead of a win-lose message

To make the game more fun, you can change the game from "win-or-lose" to awarding fictitious prizes for each score. You can offer four prizes. However, the player should win only one prize:

- If the player scores greater or equal to 16, they'll win a **new car**.
- If the player scores greater or equal to 10, they'll win a **new laptop**.
- If the player scores exactly 7, they'll win a **trip**.
- Otherwise, the player wins a **kitten**.

```csharp
Random dice = new Random();

int roll1 = dice.Next(1, 7);
int roll2 = dice.Next(1, 7);
int roll3 = dice.Next(1, 7);

int total = roll1 + roll2 + roll3;

Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");

if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3))
{
    if ((roll1 == roll2) && (roll2 == roll3))
    {
        Console.WriteLine("You rolled triples!  +6 bonus to total!");
        total += 6;
    }
    else
    {
        Console.WriteLine("You rolled doubles!  +2 bonus to total!");
        total += 2;
    }

    Console.WriteLine($"Your total including the bonus: {total}");
}

if (total >= 16)
{
    Console.WriteLine("You win a new car!");
}
else if (total >= 10)
{
    Console.WriteLine("You win a new laptop!");
}
else if (total == 7)
{
    Console.WriteLine("You win a trip for two!");
}
else
{
    Console.WriteLine("You win a kitten!");
}

/* Output:
Dice roll: 2 + 2 + 5 = 9
You rolled doubles!  +2 bonus to total!
Your total including the bonus: 11
You win a new laptop!
*/
```

The `if`, `else if`, and `else` statements allow you to create multiple exclusive conditions as Boolean expressions. In other words, when you only want one outcome to happen, but you have several possible conditions and results, use as many `else if` statements as you want. If none of the `if` and `else if` statements apply, the final `else` code block will be executed. The `else` is optional, but it must come last if you choose to include it.

### Challenge

You've been asked to add a feature to your company's software. The feature is intended to improve the renewal rate of subscriptions to the software. Your task is to display a **renewal message** when a user logs into the software system and is notified their subscription will soon end. You'll need to add a couple of **decision statements** to properly add branching logic to the application to satisfy the requirements.

Starter code:

```csharp
Random random = new Random();
int daysUntilExpiration = random.Next(12);
int discountPercentage = 0;

// Your code goes here
```

Requirements:

1. Rule 1: Your code should only display one message.

2. Rule 2: If the user's subscription will expire in 10 days or less, display the message:
    - "Your subscription will expire soon. Renew now!"

3. Rule 3: If the user's subscription will expire in five days or less, display the messages:
    - "Your subscription expires in _ days."
    - "Renew now and save 10%!"

4. Rule 4: If the user's subscription will expire in one day, display the messages:
    - "Your subscription expires within a day!"
    - "Renew now and save 20%!"

5. Rule 5: If the user's subscription has expired, display the message:
    - "Your subscription has expired."

Rule 6: If the user's subscription doesn't expire in 10 days or less, display nothing.

### Solution

```csharp
Random random = new Random();
int daysUntilExpiration = random.Next(12);
int discountPercentage = 0;

if (daysUntilExpiration == 0)
{
    Console.WriteLine("Your subscription has expired.");
}
else if (daysUntilExpiration == 1)
{
    discountPercentage = 20;
    Console.WriteLine("Your subscription expires within a day!");
}
else if (daysUntilExpiration <= 5)
{
    discountPercentage = 10;
    Console.WriteLine($"Your subscription expires in {daysUntilExpiration} days.");
}
else if (daysUntilExpiration <= 10)
{
    Console.WriteLine("Your subscription will expire soon. Renew now!");
}

if (discountPercentage > 0)
{
    Console.WriteLine("Renew now and save " + discountPercentage + "%!");
}
```

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-if-elseif-else/6-knowledge-check>

1. **Given that `int x = 5`, which of the following Boolean expressions is valid and evaluates to true?**

   - `x < 5.`
     > Incorrect. Since `x` isn't less than `5`, this expression evaluates to false.
   - `x > 5.`
     > Incorrect. Since `x` isn't greater than `5`, this expression evaluates to false.
   - `x == 5.`
     > **Correct**! Since `x` is equal to `5`, using the C# equality operator `==` in the expression evaluates to true.

2. **Which of the choices below is not a valid operator in C#?**

   - `%%.`
     > **Correct**! The double percentage-sign symbol `%%` isn't a valid C# operator.
   - `&&.`
     > Incorrect. `&&` is the C# logical AND operator.
   - `||.`
     > Incorrect. `||` is the C# logical OR operator.

3. **The following answer choices describe `if` statement syntax. Which of the descriptions is correct?**

   - `The Boolean expression evaluated by an if statement is optional.`
     > Incorrect. A Boolean expression is a required component of an `if` statement.
   - `An else statement can't be placed before an else if statement.`
     > **Correct**! An `else` can't be placed before an `else if` statement.
   - `The else statement is required when an if statement includes an else if.`
     > Incorrect. The `else` statement isn't required in order to create a valid `if` statement.
