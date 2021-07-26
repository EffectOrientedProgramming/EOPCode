# Effect-Oriented Programming Book Examples

If you want to experiment with the code examples from the book [Effect Oriented Programming](https://github.com/EffectOrientedProgramming/book), you're in the right place.

These examples are automatically extracted directly from the book.
This repository includes tests to verify that the code in the book is correct.

* TODO: Run these instructions on a clean machine.
* TODO: Complete pieces inside {{ markers }}.

# Contents

- [Basic Steps](#basic-steps)
  - [Notes](#notes)
- [Coursier](#coursier)
  - [1. Install Coursier](#1-install-coursier)
    - [Windows](#windows)
    - [Macintosh](#macintosh)
    - [Linux](#linux)
  - [2. Update Coursier](#2-update-coursier)
  - [3. Use Coursier to Install the Tools](#3-use-coursier-to-install-the-tools)
- [Using SBT](#using-sbt)
  - [Compiling](#compiling)
  - [Running a Program](#running-a-program)
  - [Automatic Command Execution](#automatic-command-execution)
  - [Exiting](#exiting)
- [Install the Example Code](#install-the-example-code)
- [Install an IDE](#install-an-ide)
  - [IntelliJ IDEA](#intellij-idea)
  - [Visual Studio Code (VSCode)](#visual-studio-code-vscode)

([TOC Generator](https://remarkablemark.org/blog/2020/12/06/markdown-table-of-contents-generator/)).

# Basic Steps

This is an overview of the setup process to use these examples. The following sections provide detailed instructions.

1. Download and install [Coursier](https://get-coursier.io/).
2. Run `cs setup`. This installs a Java Development Kit (JDK), Scala 3 {{ Does it? }}, and support tools such as the Scala Build Tool ([SBT](https://www.scala-sbt.org/)).
3. Install an Integrated Development Environment (IDE): either IntelliJ IDEA or Visual Studio Code (VSCode).
4. Install the Scala add-on for your IDE.
5. Clone/download this repository.
6. Open the `build.sbt` file in your IDE.

## Notes

1. We assume you know how to use the Command-Line Interface (CLI) for your Operating System (OS: Windows, Macintosh or Linux).
If you do not, you can find instructions [here](https://github.com/BruceEckel/AtomicKotlinExamples/blob/master/README.md#appendix-a-command-line-basics).
These instructions were written for [Atomic Kotlin](https://www.atomickotlin.com/), so Kotlin will be referenced.

2. If any terminology or processes described here are still not clear, you can usually find explanations or answers through
[Google](https://www.google.com/). For more specific issues or problems, try
[StackOverflow](http://stackoverflow.com/). Sometimes you can find installation
instructions on [YouTube](https://www.youtube.com/).

# Coursier

[Coursier](https://get-coursier.io/docs/cli-overview) is the Scala installer we use to ensure that a JVM and standard Scala tools are installed on your system.
Details are [here](https://docs.scala-lang.org/scala3/getting-started.html).

## 1. Install Coursier

The process for installing Coursier is different for each operating system.

### Windows

Run the following commands (**Note:** Use cmd.exe, not Powershell):

```
> bitsadmin /transfer cs-cli https://git.io/coursier-cli-windows-exe "%cd%\cs.exe"
> .\cs --help
```

### Macintosh

Run the following commands:

```
> curl -fLo cs https://git.io/coursier-cli-"$(uname | tr LD ld)"
> chmod +x cs
> ./cs install cs
```

### Linux

First, install `curl`:

```
> sudo apt install curl
```

Now use `curl` to install **Coursier**:

```
> curl -fLo cs https://git.io/coursier-cli-"$(uname | tr LD ld)"
> cs
```
Running the `cs` command verifies that Coursier was installed. 
If the terminal displays a message saying 'cs is not found', 
check the previous command. 

If the terminal displays a message like:

```
Warning: /home/ExamplePath/Example/coursier/bin is not in your PATH
``` 

Use the following command, replacing the `<Insert Path>` with the path from the 
above warning message:
  
```
> export PATH="$PATH:/<Insert Path>/coursier/bin"
```

For example, if the warning message is:
  
```
Warning: /home/bob/.local/share/coursier/bin is not in your PATH
``` 
  
Run this:
  
```
> export PATH="$PATH:/home/bob/.local/share/coursier/bin"
```

Then enter these commands to give execute permission to Coursier and install the 
package:
  
```
> chmod +x cs
> ./cs install cs
```

## 2. Use Coursier to Install the Needed Tools

This command installs the JDK, Scala 3, the SBT build tool, and several other tools:

```
> cs setup
```

This may take a few minutes. When prompted with a `[Y/n]` query, enter `y` for all options. 

Once installation is complete you can run a few simple tests to ensure the installation was successful:

1. java {{ show example output }}
2. javac {{ show example output }}
3. scala {{ show example output }}
4. sbt --h {{not sure if that's right, dump the help screen, show example output }}
5. {{ Other tests ... }}

 Update Coursier

Once Coursier is installed, it can be updated with:

```
> cs update cs
```

Do this periodically to make sure you have the latest Coursier version.

## 3. Using SBT

In a terminal, run the command:

```
> sbt
```

This opens the sbt shell. For this project, the prompt will look like this:

```
sbt:EffectOrientedProgramming>
```

From here, you can run the programs in your project.

## Compiling

To compile all the files in the current project, run the following inside the sbt shell:

```
sbt:EffectOrientedProgramming> compile
```

## Running a Program

(All commands here are run from within the sbt shell)

To display a list of all executables in the project:

```
sbt:EffectOrientedProgramming> run
```

To run a specific program, use `runMain`:

```
sbt:EffectOrientedProgramming> runMain programName
```

For example, the main function of the `HelloWorld` object is located in
the directory `Examples`. To run `helloWorld`:

```
sbt:EffectOrientedProgramming> run
(sbt displays number list of main programs)
Enter number: (input the index of helloWorld)
```

or

```
sbt:EffectOrientedProgramming> runMain helloWorld
```

To run a program in a package, use the format **runMain packagename.mainName**.

## Automatic Command Execution

If you precede any command with `~`, sbt automatically runs that command whenever there is a change to the associated files.
For example:

```
sbt:EffectOrientedProgramming> ~runMain helloWorld
```

automatically runs `helloWorld` whenever any of that program's files change.
Pressing the `ENTER` key stops the automated command.

## Exiting

To exit the sbt shell, press **ctrl + d**.

# Install the Example Code

Download the [zipped code repository](https://github.com/EffectOrientedProgramming/book/Examples) and unpack the archive.

# Install an IDE

## IntelliJ IDEA

1. Follow the instructions [here](https://www.jetbrains.com/help/idea/installation-guide.html)
   to install IntelliJ IDEA.

2. Start IntelliJ IDEA, and select the `File | Open` menu item.  Navigate to
   where you unzipped the repository and open the `build.sbt` file.

3. Go to the menu and select:
   `View | Tool Windows | sbt`. Right-click the directory name, and reload the sbt project.
   This should ensure your machine has all necessary plugins and extensions installed.
   
- If you get a message:
  ```
  Scalafmt configuration detected in this project
    Use scalafmt formatter
    Continue using IntelliJ formatter
  ```
  Select `Use scalafmt formatter`
  
- When you open a Scala file in IntelliJ, you might get a message in the title bar of that file:
  ```
  No Scala SDK in module
  ```
  On the right side of that message bar, you'll see:
  ```
  Setup Scala SDK
  ```
  Click on this. In the resulting dialog box, select "Create" and choose the latest Coursier version of Scala, which will be
  a version 2. The Dialog box will now look something like this:
  
  ![image](https://user-images.githubusercontent.com/1001900/126879631-6490636e-7db5-4e4f-90c6-82292ff2569f.png)
  
  Select "OK". Now go to `File | Project Structure | Global Libraries` and Choose Scala 3, like this:
  
  ![image](https://user-images.githubusercontent.com/1001900/126879808-1285e65e-e674-4a9b-9246-c86f86956e90.png)

  
## Visual Studio Code (VSCode)

TODO
