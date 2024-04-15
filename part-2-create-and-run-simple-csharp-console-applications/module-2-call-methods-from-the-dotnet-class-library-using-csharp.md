# Call methods from the .NET Class Library using `C#`

<https://learn.microsoft.com/en-us/dotnet/api/system?view=net-8.0>

## Introduction

The **C# programming language** is complemented by a vast library of functionality, enabling the creation of applications, data access, advanced mathematical operations, and much more. Mastering the navigation of this library is a crucial skill for building feature-rich applications efficiently.

Consider a scenario where you need to generate a daily report based on thousands of data files. Your code uses a random sample of the data files to calculate an approximate result, bypassing the need to analyze all the data files. But how do you generate a random number? Is this supported by `C#`? How do you set the value range for a random number, and then generate and retrieve the result?

In this module, you'll explore **class libraries** and write code that calls methods in the **.NET Class Library**. You'll understand the characteristics of methods and why methods in the .NET Class Library are designed and implemented differently. More importantly, you'll write code that uses the .NET Library methods to accomplish specific programming tasks. You'll also utilize built-in tools and online documentation to gather information about the methods you want to work with.

By the end of this module, you'll be proficient in finding classes and methods in the .NET Class Library and using them to perform common programming tasks.

## Get started with .NET Libraries

Building a **C# application** involves more than just assembling lines of code. It requires the **.NET Runtime**, which hosts and manages your code as it executes on the end user's computer. Additionally, you'll utilize the **.NET Class Library**, a prewritten collection of coding resources that can be incorporated into your applications. This unit elucidates what the .NET Class Library is and how it enhances the C# programming language.

### What is the .NET Class Library?

Just as a public library is a great resource for finding books, the **.NET Class Library** is an invaluable resource for implementing programming tasks. It's an organized collection of programming resources.

The .NET Class Library comprises thousands of classes, each containing numerous methods. For instance, it includes the `Console` class, which is essential for developers working on console applications. This class provides methods for input and output operations such as `Write()`, `WriteLine()`, `Read()`, `ReadLine()`, and many others. For example, you may already be familiar with the following code:

```csharp
Console.WriteLine("Hello, World!");
```

A class can be thought of as a container for methods, similar to sections in a public library. Developers usually group related methods together in a single class. For instance, the `System.Console` class in the **.NET Class Library** houses methods that send or receive information from a console window.

These classes and methods often enable the building of specific types of applications. For example, a large subset of classes and methods are designed for creating dynamic web applications. There are also several families of classes for building native desktop applications, and another subset for accessing databases. The .NET Class Library contains numerous classes that support specific types of applications.

There are also classes with methods that provide support in a more general way. Their utility spans across various device platforms, application frameworks, and technology areas. For instance, if you need to read or write file information, or perform trigonometry or calculus operations, there are general-purpose classes/methods available. Regardless of whether you're building applications for the web, desktop, mobile device, or the cloud, these general-purpose classes and methods are there to assist.

Having such a vast library of functionality at your disposal is a significant time-saver for you as a software developer. The classes and methods in the .NET Class Library are created by Microsoft and are readily available for use in your applications.

## Namespaces in the .NET Class Library

In C#, a **namespace** is a declarative region that provides a way to group related types such as classes, interfaces, enums, delegates, and structs. This is primarily used to organize code and to avoid naming collisions between different areas of a program or libraries.

Namespaces are hierarchical, allowing for nested namespaces, and they can span multiple files or even assemblies (DLLs). The fully qualified name of a type includes its namespace, such as `System.IO.FileStream`, where `System.IO` is the namespace and `FileStream` is the type.

Here are some key points about namespaces:

1. **Organization**: Namespaces help to organize code in a hierarchical manner. This is especially useful in large projects where keeping track of all classes and types can be challenging.
2. **Avoiding Naming Collisions**: Namespaces allow types to be organized in a way that avoids conflicts between identical type names in different areas of a program.
3. **Scoping**: Namespaces define a scope, allowing types to be organized and referenced easily.
4. **Using Directive**: The `using` directive can be used at the beginning of a file to allow the use of types in a namespace without requiring their fully qualified names. As of C# 6.0, the `System` namespace is included in the global namespace, which means you don't need to explicitly include `using System;` at the top of your files. This includes all the types defined in the `System` namespace, such as `String`, `Int32`, `Console`, and many others.
5. **Alias**: You can create an alias for a namespace with the `using` directive, which can be useful when dealing with long or complex namespace names.
6. **Global Namespace**: All types in C# reside in the global namespace, whether they are explicitly declared in a named namespace or not. Named namespaces are a subset of the global namespace. As of C# 10, global using directives can be used to import types defined in other namespaces, which are available to all files in an application.

Here's an example of how to declare a namespace and use it:
  
```csharp
// Declare a namespace
namespace MyApplication
{
    class MyClass
    {
        public void MyMethod()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
}

// Use the namespace
namespace ProgramNamespace
{
    using MyApplication;

    class Program
    {
        static void Main()
        {
            MyClass obj = new MyClass();
            obj.MyMethod();  // Outputs "Hello, World!"
        }
    }
}
```

In this example, `MyApplication` is a namespace, `MyClass` is a class within that namespace, and `MyMethod` is a method within `MyClass`. The `using` directive allows us to use `MyClass` directly in `Main`, without needing to fully qualify it as `MyApplication.MyClass`. The `using` directive is placed inside the `ProgramNamespace` to limit its scope to that namespace.

### Even data types are part of the .NET Class Library

C# data types (such as `string` and `int`) are actually made available through classes in the .NET Class Library. The C# language abstracts the connection between the data types and the .NET classes to simplify your work. However, behind the scenes, the data types are implemented just like every other class in the .NET Class Library. This connection provides your everyday variables with built-in methods that can be very helpful.

As of C# 6.0, the `System` namespace, which includes these fundamental types, is included in the global namespace. This means you don't need to explicitly include `using System;` at the top of your files to use these types. Furthermore, as of C# 10, you can use global using directives to make a namespace available to all files in an application. This means you can use types from other namespaces without needing to include a `using` directive in each file.

## How to find what you need in the .NET Class Library

Navigating the vast number of classes and methods in the .NET Class Library can seem daunting. However, there are several strategies to help you find what you need for your application.

Firstly, it's important to understand that you won't need every class and method in the .NET Class Library, much like you wouldn't need every book in a large public library. Depending on the types of projects you work on, you'll become more familiar with some parts of the .NET Class Library and less familiar with others. Over time, you'll naturally become more acquainted with the parts of the library you use most frequently. Remember, no one knows all of the .NET Class Library, not even people that work at Microsoft.

Secondly, your needs will guide your exploration. Just as you would visit a library to find a specific book, you'll research classes and methods in response to specific programming challenges. When you encounter a problem, you can use your favorite search engine to find blog posts, articles, or forums where other developers have worked through similar issues. These resources can provide valuable insights into which .NET classes and methods you might want to use, and you may even find sample code that you can adapt for your own use.

Thirdly, Microsoft provides comprehensive online documentation for C#, including a language reference and programming guide. This documentation is a reliable source of information about what methods do, how they work, and their limitations. Microsoft's documentation team works closely with the .NET Class Library's software developers to ensure its accuracy.

Finally, practical experience is one of the best ways to deepen your understanding of the .NET Class Library. As you experiment with small code projects, you'll gain hands-on experience with various classes and methods.

All software developers follow a similar process when stepping into unfamiliar territory. The process of discovery is challenging, but it's also one of the most rewarding aspects of software development.

### Check your knowledge - 1

1. **How do you find information on the .NET classes and methods you are using?**

   - `.NET Class Library.`
   > Incorrect. Although it's true that reference material on classes and methods is found in the .NET Class Library, this answer isn't complete.
   - `Developer websites.`
   > Incorrect. Although partially correct, this answer is incomplete.
   - `.NET Class Library, Google search, and developer websites.`
   > **Correct**! This answer hits the big 3: .NET Class Library, Google search, and developer websites. These tools are the best way to find information on .NET classes and methods.

## Call the methods of a .NET Class

From your very first "Hello, World!" application, you've been using C# methods, perhaps without even realizing it. That application uses the `WriteLine()` method of the `Console` class to display the "Hello, World!" message.

However, not all classes and methods are implemented in the same way. This unit covers some of the most common variants that you'll need to understand when using methods from the .NET Class Library. More importantly, you'll learn how to find and use the documentation to gain a deeper understanding of each method.

### How to call methods in the .NET Class Library

From your previous experience with the `Console.WriteLine()` method, you should already know the basics:

1. Start by typing the class name. In this case, the class name is `Console`.
2. Add the member access operator, the `.` symbol.
3. Add the method's name. In this case, the method's name is `WriteLine`.
4. Add the method invocation operator, which is a set of parentheses `()`.
5. Finally, specify the arguments that are passed to the method, if there are any, between the parentheses of the method invocation operator. In this case, you specify the text that you want the `Console.WriteLine()` method to write to the console (for example, "Hello World!").

Optionally, depending on how the developers designed and implemented the given method, you may also need to:

- Pass additional values as input parameters.
- Accept a return value.

In the next unit, you'll examine how to pass input values to a method, and how a method can be used to return a value to the calling routine.

While some methods can be called the same way that you called `Console.WriteLine()`, there are other methods in the .NET Class Library that require a different approach.

### **Stateful versus stateless methods**

In software development, the term **state** refers to the condition of the execution environment at a specific moment in time. As your code executes line by line, values are stored in variables. At any moment during execution, the current state of the application is the collection of all values stored in memory.

**Stateless (static) Methods**: These are methods that do not depend on the state of the application. They don't reference or change any values already stored in memory. The output of a stateless method depends solely on its input parameters. **Stateless methods** are also known as **static methods**. An example of a stateless method is `Console.WriteLine()`, which outputs a message to the console. It doesn't rely on or change any application state, and it performs its function and finishes without impacting the state of the application in any way.

**Stateful (instance) Methods**: These are methods that depend on or change the state of the application. They rely on values stored in memory by previous lines of code that have already been executed, or they modify the state of the application by updating values or storing new values in memory. They're also known as **instance methods**. **Stateful methods** keep track of their state in fields, which are variables defined on the class. Each new instance of the class gets its own copy of those fields in which to store state.

For example, consider a class that has a field to store the count of instances created. A method in this class that increments this count would be a stateful method, as it relies on and modifies the state of the class.

A single class can support both stateful and stateless methods. However, when you need to call stateful methods, you must first create an instance of the class so that the method can access state. This is because stateful methods are typically associated with the state of a specific instance of a class.

In summary, the main difference between stateful and stateless methods is whether they interact with or depend on the state of the application. Stateless methods are independent of the application state, while stateful methods depend on or modify it.

#### How can you determine whether you need to create an instance of a class before calling its methods?

1. **Check the method signature**: If the method is static, you don't need to create an instance of the class. If it's an instance method, you need to create an instance of the class before calling the method. You can attempt to access the method directly from the class itself. If it works, you know that it's a stateless method. The worst that can happen is that you'll get a compilation error.
2. **Check the method documentation**: The documentation for the method will specify whether it's static or an instance method. This information will help you determine whether you need to create an instance of the class.

### Creating an instance of a class

An instance of a class is called an **object**. To create a new instance of a class, you use the `new` operator. Consider the following line of code that creates a new instance of the `Random` class to create a new object called `dice`:

```csharp
Random dice = new Random();
int roll = dice.Next(1, 7);
Console.WriteLine(roll);
```

The `new` operator does several important things:

1. It first requests an address in the computer's memory large enough to store a new object based on the `Random` class.
2. It creates the new object, and stores it at the memory address.
3. It returns the memory address so that it can be saved in the `dice` variable.

From that point on, when the `dice` variable is referenced, the .NET Runtime performs a lookup behind the scenes to give the illusion that you're working directly with the object itself.

The latest version of the .NET Runtime enables you to instantiate an object without having to repeat the type name (target-typed constructor invocation). For example, the following code will create a new instance of the `Random` class:

```csharp
Random dice = new();
int roll = dice.Next(1, 7);
Console.WriteLine(roll);
```

The intention is to simplify code readability. You always use parentheses when writing a target-typed `new` expression.

### Why is the Next() method stateful?

You might be wondering why the `Next()` method was implemented as a **stateful method**? Couldn't the .NET Class Library designers figure out a way to generate a random number without requiring state? And what exactly is being stored or referenced by the `Next()` method?

These are fair questions. At a high level, computers are good at following specific instructions to create a reliable and repeatable outcome. To create the illusion of randomness, the developers of the `Next()` method decided to capture the date and time down to the fraction of a millisecond and use that to seed an algorithm that produces a different number each time. While not entirely random, it suffices for most applications. The state that is captured and maintained through the lifetime of the dice object is the seed value. Each subsequent call to the `Next()` method is rerunning the algorithm, but ensures that the seed changes so that the same value isn't (necessarily) returned.

To use the `Random.Next()` method, however, you don't have to understand how it works. The important thing to know is that some methods require you to create an instance of a class before you call them, while others do not.

### Check your knowledge - 2

1. **Which of the following represents the correct way to create a class instance?**

   - `Random dice = new Random.Next();.`
     > Incorrect. Declaring an instance of a class requires a reference to the class. In this case `Random.Next()` is a reference to the `Next()` method, not the class.
   - `Random dice = new Random();.`
     > **Correct**! Defining the type and including the `new` operator is the correct way to create a class instance.
   - `String dice = new Random();.`
     > Incorrect. The `Random` type must be used to define an instance of the `Random` class.

2. **A developer creates an instance of the Random class named coins. Which of the following code lines can they use to call the Next() method?**

   - `int money = new coins.Next();.`
     > Incorrect. The keyword `new` can't be used when calling a method.
   - `int money = Random.Next();.`
     > Incorrect. The `Random.Next()` method cannot be accessed directly (using the `Random` class) because it is a stateful method.
   - `int money = coins.Next();.`
     > **Correct**! This statement uses your instance of the `Random` class, `coins`, to return a random number.

## Return values and input parameters of methods

In the previous unit, you used a **"roll dice"** coding scenario to illustrate the difference between **stateful (instance)** and **stateless (static)** methods. That same scenario can help you to understand other important concepts about calling methods. For example:

- Handling the return value of a method.
- Passing input parameters to a method.
- Choosing an overloaded version of a method.

### Return values

**Void methods** complete their function without returning a value.

**Return methods**, on the other hand, return a value upon completion, typically the result of an operation. This return value is the method's way of communicating back to the calling code.

The `Random.Next()` method, for example, returns an `int` type with the randomly generated number. But methods can return any data type, even another class.

When calling a return method, you often assign the return value to a variable for later use. For instance:

```csharp
int roll = dice.Next(1, 7);
```

Sometimes, you might use the return value directly, like printing it to the console:

```csharp
Console.WriteLine(dice.Next(1, 7)); // Outputs a random number between 1 and 6
```

You can call a method without using its return value, but it's usually pointless. For example:

```csharp
dice.Next(1, 7);
```

In this case, ignoring the return value of `Next()` would waste the random value it generates.

### Input parameters

A method's input, known as a **parameter**, can be one or more variables, or none at all.

> **Note:** The terms 'parameter' and 'argument' are often used interchangeably. However, 'parameter' refers to the variable used inside the method, while 'argument' is the value passed when the method is called.

Most methods accept one or more input parameters. These parameters can configure the method's operation or be operated on directly. For instance, `Random.Next()` uses parameters to set the return value's range, while `Console.WriteLine()` prints its parameter directly.

A method's **signature** defines the number and data type of its parameters. The calling code must match this signature. Some methods offer options for the number and type of parameters they accept.

When a method is called, it's given **arguments** for each parameter. These arguments must match the parameter types, but their names, if used, don't need to match the parameter names in the method.

Consider the following code:

```csharp
Random dice = new Random();
int roll = dice.Next(1, 7);
Console.WriteLine(roll); // Outputs a random number between 1 and 6
```

The first code line creates a `Random` class instance named `dice`. The second line assigns a random value to an integer `roll` using `dice.Next(1, 7)`. This method call provides two arguments to set the random number's range. The final line prints `roll` to the console with `Console.WriteLine()`.

Arguments must match the data type of the method's parameters. If they don't, the C# compiler will catch the error and force a correction before the code can run. This type checking helps prevent runtime errors.

Not all methods require input parameters. For instance, `Console.Clear()` doesn't use input parameters because it simply clears the console.

### Overloaded methods

Many methods in the **.NET Class Library** have **overloaded method signatures**, allowing you to call the method with or without arguments.

An **overloaded method** is defined with multiple method signatures, providing different ways to call the method or provide different types of data.

Overloaded methods can define an input parameter using different data types. For example, `Console.WriteLine()` has 19 different overloaded versions, most of which accept different types and write the specified information to the console. Consider the following code:

```csharp
int number = 7;
string text = "seven";

Console.WriteLine(number);
Console.WriteLine();
Console.WriteLine(text);
```

In this example, you're invoking three separate overloaded versions of the `WriteLine()` method.

- The first `WriteLine()` method uses a method signature that defines an `int` parameter.
- The second `WriteLine()` method uses a method signature that defines `zero input` parameters.
- The third `WriteLine()` method uses a method signature that defines a `string` parameter.

Overloaded methods can also define a different number of input parameters, providing more control over the desired result. For example, `Random.Next()` has overloaded versions that enable you to set various levels of constraint on the randomly generated number.

Consider the following code:

```csharp
Random dice = new Random();
int roll1 = dice.Next();
int roll2 = dice.Next(101);
int roll3 = dice.Next(50, 101);

Console.WriteLine($"First roll: {roll1}");
Console.WriteLine($"Second roll: {roll2}");
Console.WriteLine($"Third roll: {roll3}");
```

The first `Next()` method doesn't set boundaries, so it returns values from `0 to 2,147,483,647` (the maximum `int` value). The second `Next()` method specifies the maximum value as an upper boundary, so it returns a random value between `0 and 100`. The third `Next()` method specifies both the minimum and maximum values, so it returns a random value between `50 and 100`.

#### Overloaded methods Recap

`Overloaded methods` are multiple methods in the **same scope** with the **same name** but *different parameters*. They can differ in parameter `type`, `number`, or `order`. Overloading allows a method to perform `slightly different tasks based on its input`.

Here's an example in C#:

```csharp
public class Example
{
    public void Display(int num) 
    {
        Console.WriteLine("Printing int: " + num);
    }

    public void Display(double num) 
    {
        Console.WriteLine("Printing double: " + num);
    }
}
```

### Use learn.microsoft.com for information about overloaded methods

The **.NET Class Library** is vast, and it can be challenging to find the right method for your needs. Fortunately, Microsoft provides comprehensive documentation for the .NET Class Library on [learn.microsoft.com](https://learn.microsoft.com/). This documentation includes detailed information about each class and method, including the method's signature, return value, and input parameters.

Documentation for each version of the method includes:

- Brief description of the method's functionality
- Method's definition
- Input parameters that the method accepts
- Return values
- Exceptions that can be raised
- Examples of the method in use
- Other remarks about the method

> The content at learn.microsoft.com is the "source of truth" for the .NET Class Library. It's important to take the time to read the documentation to understand how a given method will work.

### Check your knowledge - 3

1. **What is a return value?**

   - `It's a value type returned by a method.`
     > **Correct**! This is the correct definition of a return value.
   - `An argument in a method call is referred to as a return value inside the method.`
     > Incorrect. A parameter of a method corresponds to an argument in the method call.
   - `It's a string value.`
     > Incorrect. A return value could be a string, but it could also be an int32, a float, a custom type, or something else.

2. **What are input parameters?**

   - `Value types (or variables) inside a method.`
     > **Correct**! This is the correct definition of an input parameter.
   - `Values returned by a method.`
     > Incorrect. Input values are passed into a method, not returned from a method.
   - `The values passed into a method in the calling statement.`
     > Incorrect. The values passed to a method in the calling statement are referred to as arguments.

3. **What is an overloaded method?**

   - `A method that returns a value type.`
     > Incorrect. Returning a value does not make a method an overloaded method.
   - `A method with more than five parameters.`
     > Incorrect. An overloaded method might include more than five parameters.
   - `It is a method that supports several implementations of the method, each with a unique method signature.`
     > **Correct**! This is the correct definition of an overloaded method.

4. **How does IntelliSense help developers?**

   - `IntelliSense can help developers write code more quickly.`
     > **Correct**! IntelliSense can catch misspelling, incorrect usage, and suggest corrections. These things speed up the coding process.
   - `IntelliSense helps developers refactor their code.`
     > Incorrect. While IntelliSense can help developers with their coding, it is not intended to be used as a code refactoring tool.
   - `IntelliSense can change the "theme" of an IDE.`
     > Incorrect. IntelliSense is not used for this purpose.

## Complete a challenge activity to discover and implement a method call

Find a method of the `System.Math` class that returns the larger of two numbers.

```csharp
int firstValue = 500;
int secondValue = 600;
int largerValue;

Console.WriteLine(largerValue);
```

You can use either Visual Studio Code "Intellisense" or learn.microsoft.com to find the method and determine how to call it properly.

Use the method that you found to assign a value to the variable named `largerValue`.

You should be able to pass the two integer values, `firstValue` and `secondValue`, to the method that you found. The method should return a value of type `int` that represents the larger of the two arguments that you passed it.

You can assign the return value to `largerValue` on a new code line or on the existing code line that's used to declare `largerValue`.

Output should be the larger of the two numbers:

```txt
600
```

## Solution

Math.Max Method - <https://learn.microsoft.com/en-us/dotnet/api/system.math.max?view=net-8.0>

```csharp
int firstValue = 500;
int secondValue = 600;
int largerValue = Math.Max(firstValue, secondValue);

Console.WriteLine(largerValue);
```

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-call-methods/7-knowledge-check>

1. **What is an object?**

   - `A memory address.`
     > Incorrect. An object's memory address (location) is saved in a variable, but it isn't the same as a memory address.
   - `A stateless class.`
     > Incorrect. An object usually isn't stateless, nor is it a class.
   - `An instance of a class.`
     > **Correct**! An object represents the instantiation of a class.

2. **Which of the following statements is true?**

   - `The .NET Class Library always defines overloaded methods for every method.`
     > Incorrect. Not every method has overloaded versions.
   - `The .NET Class Library contains definitions for data types used in C#.`
     > **Correct**! The .NET Class Library is where information for C# data types can be found.
   - `The .NET Class Library includes so many classes that it actually increases development time.`
     > Incorrect. The .NET Class Library is a huge time saver for software developers.

3. **Which of the following symbols represent the method invocation operator required to execute a method?**

   - `.`
     > Incorrect. The `.` symbol is the member access operator.
   - `{}`
     > Incorrect. Curly braces are used for several reasons, but they never invoke a method.
   - `()`
     > **Correct**! The open and close parentheses are required for executing a method. The parentheses are also used when passing arguments to a method.
