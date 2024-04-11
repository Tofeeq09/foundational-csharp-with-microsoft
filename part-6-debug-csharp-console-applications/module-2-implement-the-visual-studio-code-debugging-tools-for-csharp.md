# Implement the Visual Studio Code debugging tools for `C#`

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/implement-visual-studio-code-debugging-tools/11-knowledge-check>

1. **Which section of the RUN AND DEBUG view is used to track the current point of execution within the running application?**

   - `The VARIABLES section.`
     > Incorrect. The VARIABLES section is used to view and manage variable state during a debug session.
   - `The CALL STACK section.`
     > **Correct**. The CALL STACK section is used to keep track of the current point of execution within the running application, starting with the initial point of entry into the application.
   - `The WATCH section.`
     > Incorrect. The WATCH section is used to monitor variables or expressions.

2. **Which of the following options can be used to set a breakpoint in Visual Studio Code?**

   - `Left-click in the column to the left of a line number in the code editor.`
     > **Correct**. A breakpoint can be set by positioning the mouse pointer in the column to the left of a line number and then left-clicking.
   - `Select Toggle Breakpoint on the Edit menu.`
     > Incorrect. The option to toggle breakpoints is on the Run menu, not the Edit menu.
   - `Right-click in the middle of a line of code, and then select Toggle Breakpoint.`
     > Incorrect. Right-clicking in the middle of a line of code displays a context menu, but there is no Toggle Breakpoint option provided.

3. **How can a developer disable a breakpoint in Visual Studio Code?**

   - `Click Remove Breakpoint on the Run menu.`
     > Incorrect. The Remove Breakpoint option removes the breakpoint rather than disabling it.
   - `Right-click the red dot to the left of the line number and select Disable Breakpoint.`
     > **Correct**. A breakpoint can be disabled by right-clicking the red dot that represents a breakpoint and then selecting Disable Breakpoint.
   - `Left-click the red dot to the left of the line number.`
     > Incorrect. Left-clicking the red dot that represents a breakpoint will delete the breakpoint.

4. **What is a conditional breakpoint in Visual Studio Code?**

   - `A breakpoint that only triggers when a specified condition is met.`
     > **Correct**. A conditional breakpoint is a special type of breakpoint that only triggers when a specified condition is met.
   - `A breakpoint that is triggered every time the code is run.`
     > Incorrect. A conditional breakpoint is triggered when a specified condition is met.
   - `A breakpoint that is only visible in the editor and does not affect debugging.`
     > Incorrect. A conditional breakpoint affects debugging and pauses execution when the condition is met.

5. **How can a developer create a conditional breakpoint in Visual Studio Code?**

   - `Left-click in the column to the left of a line number in the code editor.`
     > Incorrect. A left-click in the column to the left of a line number sets a standard breakpoint.
   - `Select Toggle Conditional Breakpoint on the Run menu.`
     > Incorrect. The Run menu does not include a Toggle Conditional Breakpoint option. The Run menu does include a New Breakpoint option that displays a submenu. The submenu includes a Conditional Breakpoint option.
   - `Right-click in the column to the left of a line number, and then select Add Conditional Breakpoint.`
     > **Correct**. A developer can create a conditional breakpoint by right-clicking in the column to the left of a line number, and then selecting Add Conditional Breakpoint.

6. **In a launch configuration file, what is the console attribute used for?**

   - `Specifies the working directory of the target process.`
     > Incorrect. The cwd attribute specifies the working directory of the target process.
   - `Specifies the type of debugger to use for this launch configuration.`
     > Incorrect. The type attribute specifies the type of debugger to use for this launch configuration.
   - `Specifies the type of console that's used when the application is launched.`
     > **Correct**. The console attribute specifies the type of console that's used when the application is launched. The options are internalConsole, integratedTerminal, and externalTerminal. The default setting is internalConsole.
