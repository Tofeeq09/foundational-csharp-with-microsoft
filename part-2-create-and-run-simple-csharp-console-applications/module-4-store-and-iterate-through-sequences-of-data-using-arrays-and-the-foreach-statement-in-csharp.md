# Store and iterate through sequences of data using Arrays and the foreach statement in `C#`

## Introduction

C# **arrays** provide a way to store multiple values in a single data structure. Think of it as a container that can hold numerous values. With this container, you can perform various operations such as **sorting** the values, **reversing** their order, or **looping** through each value for individual inspection.

Imagine you're part of the security team in a company that connects online sellers with commission-based advertisers. Your task is to write C# code that **iterates** through the **Order IDs** of incoming orders. The goal is to scrutinize each Order ID to detect potential **fraudulent orders**. To achieve this, you'll need to utilize arrays.

In this module, you'll delve into **creating and initializing arrays**. You'll learn how to **set and retrieve values** from array elements, with each element accessed using its **index**. You'll also construct **looping logic** that enables you to interact with each array element.

By the conclusion of this module, you'll have gained experience with your first data structure capable of holding multiple data values. Future modules will guide you on how to **sort, filter, query, aggregate**, and execute other operations on your data.

## Get started with array basics

In C#, an **array** is a robust data structure that holds a fixed number of values of a single type. The size of an array is determined at the time of its creation and cannot be changed afterwards.

Arrays in C# are **reference types**, meaning they are stored on the **heap**, a region of your computer's memory used for dynamic memory allocation. When you create an array, C# reserves a block of memory large enough to hold the array elements and returns a reference to the start of that block of memory. This is why arrays in C# are always created dynamically with the `new` keyword.

Each value in an array is called an **element**, and you can access elements through their **indices**. Array indices in C# are **zero-based**, meaning the first element is at index 0, the second element is at index 1, and so on.

The type of data that an array can store is called its **element type**. An array can store any valid C# type, including **value types** like `int`, `float`, `char`, etc., **reference types** like `string`, `object`, etc., or even other `arrays`.

Here's an example of how to declare, create, and initialize an array in C#:

```csharp
int[] numbers = new int[5] {1, 2, 3, 4, 5};
```

In this example, `int` is the element type, `[]` denotes this is an array variable, `numbers` is the name of the array, `new` is the keyword that denotes the creation of an array, and `5` is the size of the array. The values inside the curly braces `{1, 2, 3, 4, 5}` are the initial values of the array elements.

Alternatively, C# allows you to omit the `new int[5]` part when you're initializing the array with specific values. The compiler can infer the size of the array from the number of values you're using to initialize it. This leads to the same result:

```csharp
int[] numbers = {1, 2, 3, 4, 5};

// This format is also valid in C# 12 and later
// int[] numbers = new[] [1, 2, 3, 4, 5];
```

Both of these lines of code do the same thing: they declare an array of integers, create a new array instance, and initialize it with the values 1, 2, 3, 4, and 5.

## Declare and initialize arrays

In C#, declaring and initializing an array can be done in a couple of ways.

First, you can declare the array and then assign values to its elements separately:

```csharp
int[] numbers = new int[5];
numbers[0] = 1;
numbers[1] = 2;
numbers[2] = 3;
numbers[3] = 4;
numbers[4] = 5;
```

In this case, **int[]** is the type of the array, indicating that it will hold integers. **numbers** is the name of the array. **new int[5]** creates a new array instance with a length of 5. At this point, all elements in the array are **initialized** to the **default value** for the type. For integers, the **default value** is `0`, but it's important to note that the actual **default value** is `null` and it's displayed as `0` for integer types. Then, each element of the array is assigned a value individually.

Alternatively, you can declare and initialize the array in a single line:

```csharp
int[] numbers = new int[5] {1, 2, 3, 4, 5};
```

Or even more concisely:

```csharp
int[] numbers = {1, 2, 3, 4, 5};
```

In these cases, the **array** is both **declared** and **initialized** with specific values in one step. The compiler infers the size of the array from the number of values provided.

The difference between these methods is mostly a matter of style and convenience. The **single-line initialization** is more concise and easier to read, especially for small arrays with known values. The separate **declaration** and **assignment** might be more appropriate if the values are not known at the time of declaration, or if they are determined **dynamically** during the execution of your program.

### Retrieve values from elements of an array

To retrieve a value from an array, you use the **index** of the element you want to access. The index is enclosed in square brackets `[]` and placed after the array name. Here's an example:

```csharp
string[] fraudulentOrderIDs = new string[3];

fraudulentOrderIDs[0] = "A123";
fraudulentOrderIDs[1] = "B456";
fraudulentOrderIDs[2] = "C789";
// fraudulentOrderIDs[3] = "D000"; // Unhandled exception. System.IndexOutOfRangeException: Index was outside the bounds of the array.  

Console.WriteLine($"First: {fraudulentOrderIDs[0]}"); // Output: First: A123
Console.WriteLine($"Second: {fraudulentOrderIDs[1]}"); // Output: Second: B456
Console.WriteLine($"Third: {fraudulentOrderIDs[2]}"); // Output: Third: C789
```

### Reassign the value of an array

The elements of an array are just like any other variable value. You can assign, retrieve, and reassign a value to each element of the array. Here's an example:

```csharp
string[] fraudulentOrderIDs = new string[3];

fraudulentOrderIDs[0] = "A123";
fraudulentOrderIDs[1] = "B456";
fraudulentOrderIDs[2] = "C789";

Console.WriteLine($"First: {fraudulentOrderIDs[0]}"); // Output: First: A123
Console.WriteLine($"Second: {fraudulentOrderIDs[1]}"); // Output: Second: B456
Console.WriteLine($"Third: {fraudulentOrderIDs[2]}"); // Output: Third: C789

fraudulentOrderIDs[0] = "F000";

Console.WriteLine($"Reassign First: {fraudulentOrderIDs[0]}"); // Output: Reassign First: F000
```

### Garbage collection and arrays

The **Garbage Collector (GC)** in C# is a part of the **.NET runtime** that manages the automatic memory management of your application. It frees up memory that is no longer in use by your program, which helps to prevent **memory leaks**.

In the context of arrays, when an array is no longer in use (i.e., there are no more references to it), the **GC** can reclaim the memory occupied by that array. This process is automatic and usually happens when the system is low on available memory.

In your provided code, the `fraudulentOrderIDs` array is created and stored in the **heap**. As long as this array is in scope and being used, the **GC** will not touch it. However, once it goes out of scope (for example, if it was declared inside a method and the method has finished executing), and there are no other references to it, the **GC** is free to reclaim the memory.

It's important to note that the **GC** operates on its own schedule and the exact timing of when it runs is not predictable. Therefore, you should not rely on it to immediately free up memory once an object is no longer in use.

In the case of reassigning an array element as shown in your code, this does not directly involve the **GC**. The old value ("A123") is replaced with the new value ("F000"), but since strings are **immutable** in C#, the old string is not modified. Instead, a new string is created for "F000", and the array element is updated to reference this new string. The old "A123" string will be eligible for garbage collection if there are no other references to it.

### Use the Length property of an array

Depending on how the array is created, you may not know in advance how many elements an array contains. To determine the size of an array, you can use the Length property.
> **Note**: The Length property of an array is not zero-based.

```csharp
string[] fraudulentOrderIDs = { "A123", "B456", "C789" };

Console.WriteLine($"First: {fraudulentOrderIDs[0]}"); // Output: First: A123
Console.WriteLine($"Second: {fraudulentOrderIDs[1]}"); // Output: Second: B456
Console.WriteLine($"Third: {fraudulentOrderIDs[2]}"); // Output: Third: C789

fraudulentOrderIDs[0] = "F000";

Console.WriteLine($"Reassign First: {fraudulentOrderIDs[0]}"); // Output: Reassign First: F000

Console.WriteLine($"There are {fraudulentOrderIDs.Length} fraudulent orders to process."); // Output: There are 3 fraudulent orders to process.
```

### Check your knowledge - 1

1. **What is an array?**

   - A string variable.
     > Incorrect. An array isn't thought of as a string variable, although an array variable can hold a set of strings.

   - A sequence of individual data elements accessible through a single variable name.
     > **Correct**. An array data structure with a single name and multiple data locations.

   - A .NET Class Library.
     > Incorrect. Although the Array class is a part of the .NET Class Library, it isn't a .NET Class Library itself.

2. **Which of these is a correct example of creating an array and initializing it?**

   - `string[] myArray = new string[3]; myArray = "test1"; myArray = "test2"; myArray = "test3";`
     > Incorrect. Although the array myArray is declared correctly, the code statements used to assign values to the array elements are missing the array index locations.

   - `string[] myArray = string[3]; myArray[0] = test1; myArray[1] = test2; myArray[2] = test3;`
     > Incorrect. The new operator is missing from the statement used to declare the array.

   - `int[] myArray = new int[3]; myArray[0] = 1; myArray[1] = 2; myArray[2] = 3;`
     > **Correct**! The array myArray is declared correctly and the code statements used to assign values to the array elements specify the array index locations.

## Implement the foreach statement

Suppose you work for a manufacturing company. The company needs you to complete an **inventory** of your warehouse to determine the number of products that are ready to ship. In addition to the total number of finished products, you need to report the number of finished products stored in each individual bin in your warehouse, along with a **running total**. This running total will be used to create an **audit trail** so you can double-check your work and identify **"shrinkage"**.

### Looping through an array using foreach

- The `foreach` statement iterates over the collection, accessing each item in turn.
- The order of access is from the first to the last item for most collections, including arrays and lists. For an array, this means starting at index 0 and ending at index Length - 1.
- A temporary variable is used to hold the current item for each iteration of the loop. This variable takes on the value of each element in the collection one by one.
- The code block under the `foreach` declaration is executed for each item in the collection.

Here's a simple example of a foreach loop in C#:

```csharp
int[] numbers = {1, 2, 3, 4, 5};

foreach (int number in numbers)
{
    Console.WriteLine(number);
}

/* Output:
1
2
3
4
5
*/
```

In this example, the `foreach` loop iterates over the `numbers` array. For each iteration, it assigns the **current element** to the `number` variable and then executes the code block, which in this case is a call to `Console.WriteLine(number)`.

### Display the final value of sum

```csharp
int[] inventory = { 200, 450, 700, 175, 250 };
int sum = 0;
foreach (int items in inventory)
{
    sum += items;
}

Console.WriteLine($"We have {sum} items in inventory.");
```

### Create a variable to hold the current bin number and display the running total

To fulfill the final requirement of your inventory reporting project, you'll need to create a variable that will hold the current iteration of the `foreach` statement so you can display the bin and the count of finished items in that bin, along with the running total of all items of bins accounted for so far.

Inside the `foreach` code block, to increment **bin** each time the code block is executed.

To report the bin number, the number of finished products in the bin, and the running total of finished products.

This code will use your counter variable `bin`, the temporary `foreach` variable `items`, and your `sum` variable to report the current state of your inventory in a nicely formatted message.

```csharp
int[] inventory = { 200, 450, 700, 175, 250 };
int sum = 0;
int bin = 0;
foreach (int items in inventory)
{
    sum += items;
    bin++;
    Console.WriteLine($"Bin {bin} = {items} items (Running total: {sum})");
}
Console.WriteLine($"We have {sum} items in inventory.");
```

## Limitation of foreach

The `foreach` loop in C# is a powerful tool for iterating over collections that implement the `IEnumerable` or `IEnumerable<T>` interface. This includes most collection types in .NET, such as `arrays`, `lists`, `dictionaries`, `queues`, `stacks`, and even `strings` (which are enumerable as a collection of `char` values).

However, there are certain limitations and considerations to keep in mind when using `foreach`:

1. Index Access: `foreach` does not provide an index for the current item. If you need to know the index of the current item, a `for` loop is a better choice because it provides an index variable that you can use.

2. Collection Modification: `foreach` does not allow the collection to be modified during iteration. Attempting to add or remove items from the collection during iteration will result in an `InvalidOperationException`. In contrast, `for` and `while` loops do not have this restriction.

3. Complex Exit Conditions: `foreach` is designed for simple iteration over a collection. If you need complex exit conditions or need to alter the flow of the loop in ways that `break` and `continue` don't allow, a `while` loop might be a better choice because it allows for more complex conditions and control flow.

4. Backwards Iteration: `foreach` only iterates forward through the collection. If you need to iterate in reverse, a `for` loop is a better choice because you can control the increment/decrement of the index.

5. Multidimensional Arrays: `foreach` can iterate over one-dimensional arrays with ease, but it cannot directly iterate over multidimensional arrays. If you need to iterate over a multidimensional array, you would need to use nested `for` loops.

6. Custom Data Structures: If you create a custom data structure that does not implement `IEnumerable` or `IEnumerable<T>`, you cannot use `foreach` to iterate over it. You would need to implement one of these interfaces in your data structure to enable `foreach` iteration.

You can iterate through an array using a `for` loop by manually managing an index variable. Here's an example:

```csharp
int[] numbers = {1, 2, 3, 4, 5};

for (int i = 0; i < numbers.Length; i++)
{
    Console.WriteLine(numbers[i]);
}
```

You can iterate through an array using a `while` loop by manually managing an index variable. Here's an example:

```csharp
int[] numbers = {1, 2, 3, 4, 5};
int index = 0;

while (index < numbers.Length)
{
    Console.WriteLine(numbers[index]);
    index++;
}
```

While `foreach` is a powerful tool for iterating over collections, it's not always the best tool for the job. Depending on your specific requirements, a `for` or `while` loop might be a better choice.

### Complete a challenge activity for nested iteration and selection statements

> Your team has found a pattern. Orders that start with the letter "`B`" encounter fraud at a rate 25 times greater than the normal rate. You write new code that outputs the Order ID of new orders where the Order ID starts with the letter "`B`". This will be used by the fraud team to investigate further.

Declare an array and initialize it to contain the following elements:

```txt
B123
C234
A345
C15
B177
G3003
C235
B179
```

You need to evaluate each element of the array. Report the potentially fraudulent Order IDs by detecting the orders that start with the letter "B". To determine whether or not an element starts with the letter "B", use the String.StartsWith() method. Here's a simple example of how to use the String.StartsWith() method that you can adapt for your code:

```csharp
string name = "Bob";
if (name.StartsWith("B"))
{
    Console.WriteLine("The name starts with 'B'!");
}

// Output: The name starts with 'B'!

```

The output of your code should should be in the following format:

```txt
B123
B177
B179
```

## Solution

```csharp
string[] names = { "B123", "C234", "A345", "C15", "B177", "G3003", "C235", "B179" };

foreach (string name in names)
{
    if (name.StartsWith("B"))
    {
        Console.WriteLine(name);
    }
}
```

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-arrays/6-knowledge-check>

1. **Which of the following can be used to access the third element in an array?**

   - `myArray[3].`
     > Incorrect. Remember - indexes are zero-based.
   - `myArray[2].`
     > **Correct**! Indexes are zero-based, so an index of two returns the third element in an array.
   - `myArray{3}.`
     > Incorrect. Square brackets are used for array indexes and index numbers are zero-based.

2. **Which of the following choices describes the correct way to create a new integer array with three elements?**

   - `int[] myArray = new int[3];.`
     > **Correct**! This is the correct way to create an array with three elements.
   - `int[] myArray = new int[2];.`
     > Incorrect. Arrays indexes are zero based, but when declaring an array, specify the actual number of elements.
   - `int myArray = new int[3];.`
     > Incorrect. Missing a set of square brackets after the initial type specification, `int`.

3. **Which of the following `foreach` statements is syntactically correct?**

   - `foreach (int value in values).`
     > **Correct**! This `foreach` statement is defined using valid syntax.
   - `foreach (int value of values).`
     > Incorrect. The `foreach` statement doesn't include an `of` keyword.
   - `foreach (int value with values).`
     > Incorrect. The `foreach` statement doesn't include a `with` keyword.
