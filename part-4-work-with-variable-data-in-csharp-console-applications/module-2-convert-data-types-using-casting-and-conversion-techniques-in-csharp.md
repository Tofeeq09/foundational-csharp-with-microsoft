# Convert data types using casting and conversion techniques in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-convert-cast/8-knowledge-check>

1. **Which technique should be avoided when changing a string value "4.123456789" into a decimal?**

   - `Convert.ToDecimal()`
     > Incorrect. Using `ToDecimal` is a valid technique.
   - `decimal.TryParse()`
     > Incorrect. Using `TryParse` is a valid technique.
   - `(decimal)`
     > **Correct**. It isn't possible to cast a string into a decimal.

2. **What type of action is being performed when changing a `float` into an `int`?**

   - `A narrowing conversion.`
     > **Correct**. Changing a `float` into an `int` is a narrowing conversion, because `float` can store more precision data compared to `int`.
   - `A widening conversion.`
     > Incorrect. Changing a `float` into an `int` isn't a widening conversion because `float` can store more precision data than an `int` can store.
   - `An illegal conversion.`
     > Incorrect. Changing a `float` into an `int` isn't an illegal conversion. It can be accomplished, but it's with the loss of precision data.
