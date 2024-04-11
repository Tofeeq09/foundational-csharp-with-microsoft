# Challenge project - Work with variable data in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/challenge-project-work-variable-data-c-sharp/5-knowledge-check>

1. **To sort a string array, why is it important to use the `String.Trim()` method on each array element before sorting?**

   - `Only string arrays with elements trimmed with String.Trim() can sort.`
     > Incorrect. `String.Trim()` doesn't prevent or enable sorting of a string array.
   - `String.Trim() removes leading white space that would sort before numbers and letters.`
     > **Correct**. `String.Trim()` removes both leading and trailing whitespace.
   - `The array sort is noticeably faster using String.Trim() on each element.`
     > Incorrect. The array sort isn't noticeably faster using `String.Trim()`.

2. **Both `foreach` and `for` are good choices to iterate small single dimension arrays like `{"cat", "fox", "dog", "snake", "eagle"}`, but when is it best to use a `for` loop?**

   - `When the elements have alphabetical sort order.`
     > Incorrect. It is possible to sort elements effectively with either a `foreach` or `for` loop.
   - `To perform a search on each element in the array.`
     > Incorrect. A search of each element using both `foreach` and `for` is appropriate.
   - `To evaluate a specific range of elements.`
     > **Correct**. A `for` is better when index ranges that aren't the first to the last index are required.
