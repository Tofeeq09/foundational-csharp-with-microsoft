# Guided project - Work with variable data in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/guided-project-work-variable-data-c-sharp/6-knowledge-check>

1. **Which choice best describes the purpose of `TryParse()`?**

   - `To split sentences into words stored in an array.`
     > Incorrect. `TryParse()` doesn't split sentences into words.
   - `To safely test a cast operation.`
     > **Correct**. `TryParse()` returns a bool (true or false) indicating if a cast can be completed.
   - `To find a substring in a larger string.`
     > Incorrect. `TryParse()` doesn't find a substring in a larger string.

2. **For the code `decimal.TryParse(numberString, out myConvert)` when the type of `numberString` is a `String`. Which best describes the value type for `myConvert` when the `TryParse()` is successful?**

   - `A string representing numeric digits.`
     > Incorrect. A constant might be used to replace a magic string or number, but they aren't the same thing.
   - `A Boolean value.`
     > Incorrect. The `TryParse()` returns a boolean value, but the `out` variable `myConvert` isn't a Boolean.
   - `A decimal`
     > **Correct**. For `decimal.TryParse()` the `out` variable, `myConvert` is a decimal.
