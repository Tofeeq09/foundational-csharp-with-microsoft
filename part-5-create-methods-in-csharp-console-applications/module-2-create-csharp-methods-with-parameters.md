# Create `C#` methods with parameters

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/create-c-sharp-methods-parameters/8-knowledge-check>

1. **Which of the following method signatures correctly defines 3 integer parameters?**

   - `void Multiply(int a, b, c)`
     > Incorrect. The data type for each parameter must be included.
   - `void Multiply(int a, int b, int c)`
     > **Correct**! The data type for each parameter is included and parameters are comma separated.
   - `void Multiply(int a; int b; int c)`
     > Incorrect. Parameters should be separated by commas.

2. **Given the method signature, `void Print(string name, string number = "", bool member = false)`, which of the following options correctly uses named and optional arguments?**

   - `Print("Tony", member: true);`
     > **Correct**! The optional argument is included using the parameter name followed by a `:`
   - `Print(number: "555", member: false)`
     > Incorrect. All required arguments must be included.
   - `Print("Tony", false)`
     > Incorrect. `false` needs to be a named argument using the parameter name `member`.

3. **Given the following method signature, `void SetHealth(string health)`, why don't operations inside the method affect the original input string `health`?**

   - `The string data type is pass by value.`
     > Incorrect. Strings are pass by reference, but they're immutable so the value can't be altered once assigned.
   - `The method code must be incorrect.`
     > Incorrect. Strings are pass by reference, but they're immutable so the value can't be altered once assigned.
   - `Strings can't be altered once assigned, they can only be overwritten with a new value.`
     > **Correct**! Strings are pass by reference, but they're immutable and can't be altered once assigned.
