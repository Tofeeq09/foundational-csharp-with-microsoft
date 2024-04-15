# Create readable code with conventions, whitespace, and comments in `C#`

The code that you write should communicate your intent to both the compiler and other developers who may need to read your code. And since you're the developer who will be reading your code most often, sometimes months after you originally wrote it, it's in your best interest to write code that's clear and easy to understand. Remember, you may write code once, but you will need to read it many times.

Suppose you've been asked to write some code for another group of developers. You meet with them to discuss the specification and the assignment is clear. After the meeting they tell you that you'll be working independently during development. Once you're done, you'll hand off your code to the other group. The coding task isn't beyond your skill level, but you've never had to write code that someone else will be maintaining. The team told you that as long as you to follow the standard coding conventions for C#, there should be no problem. You make plans to review the C# coding conventions that relate to the code you're going to work on.

In this module, you'll learn how to:

- Choose names for your variables that describe their purpose and intent.
- Add code comments that document the higher-level requirements and your approach in code, as well as to temporarily instruct the compiler to ignore lines of code.
- Use whitespace to help convey the relationship of individual lines of code.

## Choose variable names that follow rules and conventions

### Variable name rules

There are some variable naming rules that are enforced by the C# compiler.

- Variable names can contain alphanumeric characters and the underscore character. Special characters like the pound `#`, the dash `-`, and the dollar sign `$` are not allowed.
- Variable names must begin with an alphabetical letter or an underscore, not a number. Developers use the underscore for a special purpose, so try to not use that for now.
- Variable names must NOT be a C# keyword. For example, these variable name declarations won't be allowed: `float float;` or `string string;`.
- Variable names are case-sensitive, meaning that `string MyValue;` and `string myValue;` are two different variables.

### Variable name conventions

Conventions are widely accepted practices within the software development community. Although not mandatory, these conventions enhance code readability and maintainability. It's beneficial to adopt these conventions into your coding habits.

- Variable names should adhere to camel case. This naming convention starts with a lower-case letter at the beginning of the first word and an upper-case letter at the beginning of each subsequent word. For instance: `string thisIsCamelCase;`.
- Variable names should be descriptive and meaningful within your application context. Choose a name that signifies the kind of data it will hold, not the data type. For instance: `bool orderComplete;`, NOT `bool isComplete;`.
- Variable names should be composed of one or more full words. Avoid contractions as they may obscure the variable's purpose to others reading your code. For instance: `decimal orderAmount;`, NOT `decimal odrAmt;`.
- Variable names should not include the data type. While you might encounter advice to use a style like `string strMyValue;`, this practice has fallen out of favor for good reasons.

The `string firstName;` example adheres to all these rules and conventions, assuming it's used to store data representing someone's first name.

```csharp
char userOption;

int gameScore;

float particlesPerMillion;

bool processedCustomer;
```

The above rules and conventions apply to local variables, which are scoped within a method body or used in console applications with top-level statements.

Remember, different constructs in your applications may have their own conventions. For instance, classes, a common construct in C# programming, have their own associated conventions.

### Check your knowledge - 1

1. **Which of the following demonstrates recommended guidelines for naming a variable in camel case?**

   - `UserOption.`
     > Incorrect. In camel case formatting the first letter is lower case.
   - `user Option.`
     > Incorrect. All variable names must have consecutive letters, no spaces.
   - `userOption.`
     > **Correct**! This is the correct way to use camel case for a variable.

## Create effective code comments

Code comments may not seem useful at first, but they serve three key purposes:

1. **Clarifying Intent:** Code comments are useful for explaining the intent or thought process behind a challenging set of coding instructions. This can be particularly helpful for your future self or other developers who might work on your code.

2. **Temporarily Removing Code:** If you want to try a different approach but aren't ready to permanently delete your existing code, you can comment it out. Once you're confident that your new code works as expected, you can safely delete the old, commented-out code.

3. **Adding Reminders:** You can use code comments to add reminders like `TODO` to revisit a particular section of code later. This can be useful when you spot a potential issue while working on another feature. Instead of ignoring the issue, you can mark it for later investigation.

> **Note:** Code comments should be used to explain what the code cannot. Developers often update their code but forget to update the comments. It's best to use comments to explain higher-level concepts rather than detailing how each individual line of code works.

Never trust comments. They may not reflect the current state of the code after many changes and updates.

### Comment types

There are two types of comments in C#:

1. **Single-line comments:** These comments start with `//` and continue until the end of the line. They are useful for adding short comments to a single line of code.

   ```csharp
   // This is a single-line comment
   int myValue = 10; // This is another single-line comment
   ```

2. **Multi-line comments:** These comments start with `/*` and end with `*/`. They are useful for adding comments to multiple lines of code.

   ```csharp
    /*
    This is a multi-line comment
    that spans multiple lines
    */
    ```

### Testing code with comments

```csharp
string firstName = "Bob";
int widgetsPurchased = 7;
// Testing a change to the message.
// int widgetsSold = 7;
// Console.WriteLine($"{firstName} sold {widgetsSold} widgets.");
Console.WriteLine($"{firstName} purchased {widgetsPurchased} widgets.");
```

Notice that the code comments are used to document the potential change being made, and to temporarily disable the old message as you **test** the new message. Your next step will be to test your update. If you're satisfied with the new code, you can safely delete the old code that was commented out. This is a **safer**, more methodical approach to modifying working code until you're convinced that you're ready to permanently remove it.

### Case 1

```csharp
Random random = new Random();
string[] orderIDs = new string[5];
// Loop through each blank orderID
for (int i = 0; i < orderIDs.Length; i++)
{
    // Get a random value that equates to ASCII letters A through E
    int prefixValue = random.Next(65, 70);
    // Convert the random value into a char, then a string
    string prefix = Convert.ToChar(prefixValue).ToString();
    // Create a random number, pad with zeroes
    string suffix = random.Next(1, 1000).ToString("000");
    // Combine the prefix and suffix together, then assign to current OrderID
    orderIDs[i] = prefix + suffix;
}
// Print out each orderID
foreach (var orderID in orderIDs)
{
    Console.WriteLine(orderID);
}
```

Given the comments, you might be able to figure out what the code is doing (assuming the comments accurately describe the current state and were updated as the code was updated). But can you guess why this code exists? Wouldn't it be helpful if there was some explanation at the top of the code file that provided some context and described its purpose?

There are two main issues with these comments:

1. **Explaining Obvious Functionality:** The comments unnecessarily explain the functionality of individual lines of code. These are considered low-quality comments as they merely explain how C# or methods of the .NET Class Library work. If a reader is unfamiliar with these concepts, they can refer to resources like learn.microsoft.com or IntelliSense.

2. **Lack of Context:** The comments don't provide any context about the problem the code is solving. These are considered low-quality comments because they don't give the reader any insight into the purpose of the code, especially in relation to the larger system.

### Case 2

```csharp
/*
  The following code creates five random OrderIDs
  to test the fraud detection process.  OrderIDs 
  consist of a letter from A to E, and a three
  digit number. Ex. A123.
*/
Random random = new Random();
string[] orderIDs = new string[5];

for (int i = 0; i < orderIDs.Length; i++)
{
    int prefixValue = random.Next(65, 70);
    string prefix = Convert.ToChar(prefixValue).ToString();
    string suffix = random.Next(1, 1000).ToString("000");

    orderIDs[i] = prefix + suffix;
}

foreach (var orderID in orderIDs)
{
    Console.WriteLine(orderID);
}
```

Notice that the code is already less cluttered.

A comment's usefulness is subjective. In all matters related to code readability, you should use your best judgment. Do what you think is best to improve the clarity of your code.

## Use whitespace to make your code easier to read

Print and web designers know that cramming too much information into a small space can overwhelm the viewer. They strategically use whitespace, or negative space, to break up information and enhance the viewer's ability to absorb the main message of their work.

Similarly, developers can use whitespace strategically when writing code in an editor. By using whitespace to convey meaning, they can enhance the clarity and intent of their code.

### What is whitespace?

In the context of C# or any text editor, "**whitespace**" refers to any character or series of characters that represent horizontal or vertical space in typography. It's the portion of a page left unmarked, including spaces between words, margins, or space between lines (leading). In C#, whitespace characters can be created by pressing the space bar, tab key, and enter key, which produce space, tab, and newline characters respectively.

Whitespace is significant in text editors for improving readability and separating code elements from each other. However, in C#, the compiler largely ignores most whitespace, meaning spaces, tabs, and newlines generally do not affect how the code is executed. This allows developers to format their code in a way that is easy to read and understand, without affecting the program's functionality.

For example, you can use whitespace to **indent** your code, aligning similar elements to make the structure of your code more apparent. You can also use it to separate sections of your code, making it easier to visually distinguish between different parts of your program.

However, it's important to note that while the C# compiler ignores most whitespace, there are situations where whitespace is significant. For instance, whitespace is necessary to separate keywords, variable names, and other identifiers from each other. Without it, the compiler wouldn't be able to tell where one ends and the next begins.

In summary, while the C# compiler mostly ignores whitespace, it plays a crucial role in making your code more **readable** and **maintainable**. Therefore, it's important to use it judiciously and consistently throughout your code.

### Add code to illustrate how whitespace is ignored by the C# compiler

```csharp
// Example 1:
Console
.
WriteLine
(
"Hello Example 1!" // This is a comment
)
;

// Example 2:
string firstWord="Hello";string lastWord="Example 2";Console.WriteLine(firstWord+" "+lastWord+"!"); // This is a comment
```

These two code examples illustrate two vital ideas:

1. Whitespace doesn't matter to the compiler. However ...
2. Whitespace, when used properly, can significantly enhance your ability to read and comprehend the code.

You likely write your code once, but need to read the code multiple times. Therefore, you should focus on the **readability** of the code you write. Over time, you'll get a feel for when and how to use whitespace, such as the space character, tabs, and new lines.

Here are some early guidance:

- Each complete command (a statement) belongs on a separate line.
- If a single line of code becomes long, you can break it up. However, you should avoid arbitrarily splitting up a single statement to multiple lines until you have a good reason to do so.
- Use a space to the left and right of the assignment operator.

### Convention

```csharp
Random dice = new Random();
int roll1 = dice.Next(1, 7);
int roll2 = dice.Next(1, 7);
int roll3 = dice.Next(1, 7);
int total = roll1 + roll2 + roll3;
Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");
if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3)) {
    if ((roll1 == roll2) && (roll2 == roll3)) {
        Console.WriteLine("You rolled triples!  +6 bonus to total!");
        total += 6; 
    } else {
        Console.WriteLine("You rolled doubles!  +2 bonus to total!");
        total += 2;
    }
}
```

Notice that this code doesn't include much whitespace. This code will be used to illustrate an approach for adding whitespace to your applications. Effective whitespace should make it easier to understand what your code is doing.

There are two features of this code to take note of:

1. There's no **vertical whitespace** in this code example. In other words, there are no empty lines separating the lines of code. It all runs together into one dense code listing.
2. The code blocks, as defined by the opening and closing curly brace symbols `{ }`, are compressed together, making their boundaries difficult to visually discern.

Generally speaking, to improve readability, you should introduce a blank line between two, three, or four lines of code that do similar or related things.

Phrasing your code using vertical whitespace is subjective. It's possible two developers won't agree on what is most readable, or when to add whitespace. Use your **best judgment**.

```csharp
Random dice = new Random();

int roll1 = dice.Next(1, 7);
int roll2 = dice.Next(1, 7);
int roll3 = dice.Next(1, 7);

int total = roll1 + roll2 + roll3;
Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");

if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3)) {
    if ((roll1 == roll2) && (roll2 == roll3)) {
        Console.WriteLine("You rolled triples!  +6 bonus to total!");
        total += 6; 
    } else {
        Console.WriteLine("You rolled doubles!  +2 bonus to total!");
        total += 2;
    }
}
```

Your first line of whitespace is used to separate the declaration of the `dice` variable from the code lines used to assign values to your `roll` variables. This separation makes it easier to see how `dice` is being used in your code.

Your next line of whitespace separates the declaration of your `roll` variables from the declaration of `total`. Grouping the declaration of your three `roll` variables is helpful in two ways. First, it creates a group of code lines that includes related variables. Second, the variable names are so similar and the declaration follows the same pattern. So, grouping them together draws your eye to the similarities and helps to expose the differences.

Finally, your third line of whitespace separates another group of related statements from your nested `if` statements. The group of statements that includes the declaration of `total` and the `Console.WriteLine()` method is related by purpose rather than appearance. Your code is focused on the `total` value achieved by the three dice and whether the roll included doubles or triples. These lines are related because you need to calculate `total` and report the results of the roll to the user.

Some developers might argue that you should add an empty line in between the declaration of `total` and the `Console.WriteLine()`. Again, the choice of whitespace is up to your **best judgment**. You should decide which is more readable for you and use that style consistently.

All that you have left is the `if` statement. You can examine that now.

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
```

The `{` and `}` symbols create code blocks. Many C# constructs require code blocks. These symbols should be placed on a separate line so that their boundaries are clearly visible and readable.

Furthermore, it's important to use the tab key to line up the code block symbols under the keyword they belong to. For example, notice the line of code that starts with the keyword `if`. Below that line is the `{` symbol. This alignment makes it easy to understand that the `{` "belongs to" the `if` statement. Furthermore, the last `}` symbol lines up with the `if` statement as well. The combination of alignment and indentation makes it easy to understand where the code block begins and ends.

The code lines inside of this code block are indented, indicating that they "belong" to this code block.

You follow a similar pattern with the inner `if` statement and `else` statement, and the code inside of those code blocks.

> Not everyone agrees with this style guidance for including whitespace. However, you should consider using this guidance as a **starting point** when writing code. In the future, you can be purposeful when making a decision to deviate from this guidance.

## Complete a challenge activity to improve code readability

In this challenge, you'll use the techniques you learned in this module to improve the readability of a code sample. You are provided with a code sample that is poorly styled and commented. Your goal is to update the code using style guidelines for variable names, code comments, and whitespace to improve code readability.

Starter code:

```csharp
string str = "The quick brown fox jumps over the lazy dog.";
// convert the message into a char array
char[] charMessage = str.ToCharArray();
// Reverse the chars
Array.Reverse(charMessage);
int x = 0;
// count the o's
foreach (char i in charMessage) { if (i == 'o') { x++; } }
// convert it back to a string
string new_message = new String(charMessage);
// print it out
Console.WriteLine(new_message);
Console.WriteLine($"'o' appears {x} times.");
```

## Solution

```csharp
/*
   This code reverses a message, counts the number of times 
   a particular character appears, then prints the results
   to the console window.
 */

string originalMessage = "The quick brown fox jumps over the lazy dog.";

char[] message = originalMessage.ToCharArray();
Array.Reverse(message);

int letterCount = 0;

foreach (char letter in message)
{
    if (letter == 'o')
    {
        letterCount++;
    }
}

string newMessage = new String(message);

Console.WriteLine(newMessage);
Console.WriteLine($"'o' appears {letterCount} times.");
```

This code is merely "one possible solution". You may have come up with some different variable names and different vertical spacing and tab indentation. Here's a list of changes that were made:

- The code includes a higher-level description of what the entire code listing is attempting to accomplish in a multi-line comment at the top. You could argue that this is a small improvement over the original code comments, however, given the challenge's description of the code, there wasn't much more context available.
- The individual comments were removed because they weren't providing any real insight into the code's purpose or function.
- Several blank lines were added to improve the phrasing of the code listing. Keep code lines together when they appear similar, or when they work with each other to accomplish a small task.
- Line feeds and tabs were added to improve the appearance of the `foreach` statement and the `if` statement.
- Local variable naming conventions were applied to better convey the purpose of each value.

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-readable-code/>

1. **Which of the following demonstrates recommended guidelines for naming a variable?**

   - `my-string.`
     > Incorrect. A variable can't contain the dash `-` character. Also, the name isn't descriptive of its purpose.
   - `initialMessage$.`
     > Incorrect. A variable can't contain the dollar sign `$` character.
   - `initialMessage.`
     > **Correct**! This is the appropriate camel case for a variable name and the name is descriptive.

2. **Which of the following is a bad reason to use a code comment?**

   - `To describe the high-level intent of the code.`
     > Incorrect. Describing the high-level intent is a good reason to use a code comment.
   - `To explain how a new C# keyword works.`
     > **Correct**! Comments should not be used for this reason.
   - `To temporarily comment out a line of code while evaluating a feature in a different way.`
     > Incorrect. Temporarily commenting out a line of code before deleting it is a good reason to use a code comment.

3. **Which of the following statements about using whitespace in code is true?**

   - `Reducing the amount of whitespace will improve code performance (execution speed).`
     > Incorrect. Whitespace doesn't impact performance.
   - `Whitespace should be used every two or three lines to separate code lines.`
     > Incorrect. Arbitrarily adding whitespace every two or three lines won't necessarily improve the readability of your code.
   - `Whitespace should be used judiciously to improve the readability of your code.`
     > **Correct**! Whitespace should be used to improve core readability.
