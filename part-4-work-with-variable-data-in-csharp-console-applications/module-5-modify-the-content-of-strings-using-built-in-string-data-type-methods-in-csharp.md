# Modify the content of strings using built-in string data type methods in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-modify-content/7-knowledge-check>

1. **Which method finds the next index of either the `-` char, the `=` char, or the `_` char?**

   - `IndexOfAny()`
     > **Correct**. Use `IndexOfAny()` to retrieve the next index for any of several chars in a string.
   - `Remove()`
     > Incorrect. `Remove()` method doesn't return an index.
   - `IndexOf()`
     > Incorrect. `IndexOf()` could be used to find the position of a single char in a string, but not any of several chars.

2. **What is a constant variable?**

   - `A magic string or number.`
     > Incorrect. A constant might be used to replace a magic string or number, but they aren't the same thing.
   - `A variable whose name must match its value.`
     > Incorrect. A constant's value is not constrained by its name.
   - `A value that once initialized can never be changed.`
     > **Correct**. A constant variable can never be changed, once initialized.
