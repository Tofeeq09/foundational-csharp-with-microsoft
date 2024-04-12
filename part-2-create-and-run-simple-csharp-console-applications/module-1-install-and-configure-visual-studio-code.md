# Install and configure Visual Studio Code

<https://code.visualstudio.com/docs/csharp/get-started>

## Introduction

Software development is more than just writing code, it's a process. Larger coding projects can take months or even years to complete and can be complex. The process of writing, debugging, testing, updating/versioning, and releasing code is a significant undertaking. To help with this process, developers use a specialized tool known as an `integrated development environment` (`IDE`).

An `IDE` typically includes a suite of **tools that support the software development process** from beginning to end, a process known as the development lifecycle. The IDE tools enable the developer to work more efficiently and can help the developer, or team of developers, to write, debug, test, publish, and version their code more easily. A good IDE is a programmer's best friend.

Suppose you're interested in getting started with C# application development. Your first step is to select a programming environment. After researching the available options online, you determine that Visual Studio Code is one of the most popular code editors among C# developers. You're happy to see that Visual Studio Code is quick and easy to install, and that it supports numerous extensions to enhance developer productivity. You also take a look at the full Visual Studio product, which provides even more features for professional developers. Both products include a free option. After consulting a developer friend, you decide that Visual Studio Code will provide all of the tools that you need to get started. You make plans to begin setting up your development environment with Visual Studio Code.

**Visual Studio Code** is a lightweight but powerful source code editor that runs on your desktop and is available for `Windows`, `macOS` and `Linux`. It comes with built-in support for `JavaScript`, `TypeScript` and `Node.js` and has a rich ecosystem of extensions for other languages and runtimes (such as `C++`, `C#`, `Java`, `Python`, `PHP`, `Go`, `.NET`).

A **language** is a set of syntactic and semantic rules used to instruct a computer. Examples include `JavaScript`, `TypeScript`, `C++`, `C#`, `Java`, `Python`, `PHP`, and `Go`. These languages have their own syntax, semantics, and constructs for defining variables, functions, and structures.

A **runtime**, on the other hand, is the environment in which programs or scripts are executed. It includes everything necessary to run a program, including an interpreter or a compiler, a set of libraries, and other environment variables. For example, `Node.js` is a runtime for executing `JavaScript` code outside of a browser. `.NET` is a runtime that can execute applications written in multiple languages, including `C#` and `F#`.

**.NET** is a comprehensive, open-source, cross-platform developer platform used for building a wide variety of applications. It's an ecosystem that includes:

- **Programming Languages**: .NET supports several languages, including `C#`, `F#`, and `Visual Basic`.

- **.NET Runtime**: Also known as the `Common Language Runtime` (`CLR`), it manages the execution of .NET programs, providing services like automatic memory management (garbage collector), security boundaries, and type safety.

- **Base Libraries and Application Framework**: .NET includes a set of standard `class libraries` and a common type system that provide reusable types and methods for developers.

- **Toolchain**: .NET comes with a powerful toolchain, including a `just-in-time compiler`, SDKs, and the `dotnet CLI`, simplifying the process of developing, building, and running applications.

In essence, .NET is not just about the runtime or the languages; it's a complete package that provides everything you need to develop robust applications.

## Create, build, and run your application

The **.NET software development kit (SDK)** includes a **command-line interface (CLI)** that can be accessed from **Visual Studio Code's integrated Terminal**. Throughout this training, you'll use `.NET CLI` commands to create new console applications, build your project code, and run your applications.

For instance, the `.NET CLI` command below creates a new console application in the specified folder location:

```bash
dotnet new console -o ./CsharpProjects/TestProject
```

A CLI command is structured into three parts:

1. **The Driver**: `dotnet` in this example.
2. **The Command**: `new console` in this example.
3. **The Command Arguments**: `-o ./CsharpProjects/TestProject` in this example.

Command arguments are optional parameters that provide additional information. The previous command could be run without specifying the optional folder location, like so:

```bash
dotnet new console
```

In this case, the new console application would be created in the current folder location.

```txt
Usage: dotnet [runtime-options] [path-to-application] [arguments]

Execute a .NET application.

runtime-options:
  --additionalprobingpath <path>   Path containing probing policy and assemblies to probe for.
  --additional-deps <path>         Path to additional deps.json file.
  --depsfile                       Path to <application>.deps.json file.
  --fx-version <version>           Version of the installed Shared Framework to use to run the application.
  --roll-forward <setting>         Roll forward to framework version  (LatestPatch, Minor, LatestMinor, Major, LatestMajor, Disable).
  --runtimeconfig                  Path to <application>.runtimeconfig.json file.

path-to-application:
  The path to an application .dll file to execute.

Usage: dotnet [sdk-options] [command] [command-options] [arguments]

Execute a .NET SDK command.

sdk-options:
  -d|--diagnostics  Enable diagnostic output.
  -h|--help         Show command line help.
  --info            Display .NET information.
  --list-runtimes   Display the installed runtimes.
  --list-sdks       Display the installed SDKs.
  --version         Display .NET SDK version in use.

SDK commands:
  add               Add a package or reference to a .NET project.
  build             Build a .NET project.
  build-server      Interact with servers started by a build.
  clean             Clean build outputs of a .NET project.
  format            Apply style preferences to a project or solution.
  help              Show command line help.
  list              List project references of a .NET project.
  msbuild           Run Microsoft Build Engine (MSBuild) commands.
  new               Create a new .NET project or file.
  nuget             Provides additional NuGet commands.
  pack              Create a NuGet package.
  publish           Publish a .NET project for deployment.
  remove            Remove a package or reference from a .NET project.
  restore           Restore dependencies specified in a .NET project.
  run               Build and run a .NET project output.
  sdk               Manage .NET SDK installation.
  sln               Modify Visual Studio solution files.
  store             Store the specified assemblies in the runtime package store.
  test              Run unit tests using the test runner specified in a .NET project.
  tool              Install or manage tools that extend the .NET experience.
  vstest            Run Microsoft Test Engine (VSTest) commands.
  workload          Manage optional workloads.

Additional commands from bundled tools:
  dev-certs         Create and manage development certificates.
  fsi               Start F# Interactive / execute F# scripts.
  user-jwts         Manage JSON Web Tokens in development.
  user-secrets      Manage development user secrets.
  watch             Start a file watcher that runs a command when files change.

Run 'dotnet [command] --help' for more information on a command.
```

### Running your application

After creating a new console application, you can navigate to the project folder and run the application using the `dotnet run` command:

```bash
dotnet run
```

The `dotnet run` command runs source code without any explicit compile or launch commands. It provides a convenient option to run your application from the source code with one command. It's useful for fast iterative development from the command line. The command depends on the dotnet build command to build the code.

## Knowledge check - <https://learn.microsoft.com/en-gb/training/modules/install-configure-visual-studio-code/8-knowledge-check>

1. **Which area of the Visual Studio Code user interface is used to write code?**

   - `Explorer.`
     > Incorrect. The Explorer view enables developers to select project files and folders.
   - `Extensions.`
     > Incorrect. The Extensions view enables developers to install tools that support software languages and help with all sorts of tasks.
   - `Editor.`
     > **Correct**! The Editor is the main area where developers write code.

2. **Which of the following tools is required to run command line interface commands such as `dotnet run`?**

   - `Visual Studio Code.`
     > Incorrect. The Visual Studio Code integrated Terminal panel does support running command line interface commands, but other command line tools could be used.
   - `C# Dev Kit.`
     > Incorrect. The C# Dev Kit and associated extensions published by Microsoft provide support developing and debugging C# projects, but they don't enable running the `dotnet` CLI commands.
   - `The .NET SDK.`
     > **Correct**! The .NET SDK is required in order to run .NET command line interface commands such as `dotnet`.
