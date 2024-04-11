# Store and iterate through sequences of data using Arrays and the foreach statement in `C#`

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
