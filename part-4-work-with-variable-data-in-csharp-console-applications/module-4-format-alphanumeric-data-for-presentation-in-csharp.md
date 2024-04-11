# Format alphanumeric data for presentation in `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/csharp-format-strings/7-knowledge-check>

1. **For the C# code `Console.WriteLine("C110".PadLeft(6, '0'));`, which is the expected output?**

   - `C11000`
     > Incorrect. `.PadLeft(6, '0')` doesn't append zeros to the right side of the string.
   - `C110000000`
     > Incorrect. `.PadLeft(6, '0')` won't append zeros to the right side of a string and won't append after the string reaches six characters long.
   - `00C110`
     > **Correct**. `.PadLeft(6, '0')` appends zeros to the left side of a string until the string is six characters long.

2. **Which format specifier presents a decimal value with the following format to an en-US audience: 12,345.67**

   - `0:C`
     > Incorrect. Though it looks similar, the numeric value is not necessarily currency.
   - `0:H`
     > Incorrect. `H` isn't a known format specifier.
   - `0:N2`
     > **Correct**. `N2` is the correct format specifier.

3. **Which character must be used as a directive to perform string interpolation?**

   - `$`
     > **Correct**. The `$` directive is used to perform string interpolation.
   - `@`
     > Incorrect. `@` is used to create a verbatim string literal, and doesn't perform string interpolation.
   - `%`
     > Incorrect. `%` is used for math to return the remainder (modulus), but isn't a valid directive for string interpolation.
