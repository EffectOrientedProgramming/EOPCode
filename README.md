# Effect Oriented Programming Examples

If you want to experiment with the code examples from the book [Effect Oriented Programming](https://github.com/EffectOrientedProgramming/book), you're in the right place.

These examples are automatically extracted directly from the book.
This repository includes tests to verify that the code in the book is correct.

# Contents

- [Basic Steps](#basic-steps)
  - [Notes](#notes)
- [Coursier](#coursier)
  - [1. Install Coursier](#1-install-coursier)
    - [Windows](#windows)
    - [Macintosh](#macintosh)
    - [Linux](#linux)
  - [2. Update Coursier](#2-update-coursier)
  - [3. Install Tools Using Coursier](#3-install-tools-using-coursier)
- [Using SBT](#using-sbt)
- [Installing an IDE](#installing-an-ide)
  - [IntelliJ IDEA](#intellij-idea)
  - [Visual Studio Code (VSCode)](#visual-studio-code-vscode)

([TOC Generator](https://remarkablemark.org/blog/2020/12/06/markdown-table-of-contents-generator/)).

# Basic Steps

1. Download and install [Coursier](https://get-coursier.io/).
2. Run `cs setup`. This installs a Java Development Kit (JDK), Scala 3 {{ Does it? }}, and support tools such as the Scala Build Tool ([SBT](https://www.scala-sbt.org/)).
3. Install an Integrated Development Environment (ID): either IntelliJ IDEA or Visual Studio Code (VSCode).
4. Install the Scala add-on for your IDE.
5. Clone/download this repository.
6. Open the `build.sbt` file in your IDE.

## Notes

1. We assume you know how to use the Command-Line Interface (CLI) for your Operating System (OS: Windows, Mac or Linux).
If you do not, you can find instructions [here](https://github.com/BruceEckel/AtomicKotlinExamples/blob/master/README.md#appendix-a-command-line-basics).
These instructions were written for [Atomic Kotlin](https://www.atomickotlin.com/), so Kotlin will be referenced.

2. If any terminology or processes described here are still not clear, you can usually find explanations or answers through
[Google](https://www.google.com/). For more specific issues or problems, try
[StackOverflow](http://stackoverflow.com/). Sometimes you can find installation
instructions on [YouTube](https://www.youtube.com/).

# Coursier

[Coursier](https://get-coursier.io/docs/cli-overview) is the Scala installer we use to ensure that a JVM and standard Scala tools are installed on your system.
Further instructions are found [here](https://docs.scala-lang.org/scala3/getting-started.html).

## 1. Install Coursier

The process for installing Coursier is different for each operating system.
In each case, the installation process also sets the **PATH** {{ Is this correct? }}.

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
> rm cs
```

### Linux

We use `curl`.
To install `curl`:

```
> sudo apt install curl
```

To install **Coursier**:

```
> curl -fLo cs https://git.io/coursier-cli-"$(uname | tr LD ld)"
> chmod +x cs
> ./cs install cs
> rm cs
```

## 2. Update Coursier


Once Coursier is installed, it can be updated with:

```
> cs update cs
```

Do this periodically to make sure you have the latest Coursier version.

## 3. Install Tools Using Coursier

This command installs the JDK, Scala 3, the SBT build tool, and several other tools:

```
> cs setup
```

This may take a few minutes.

Once installation is complete you can run a few simple tests to ensure the installation was successful:

1. TEST 1 TBD
2. TEST 2 TBD
3. etc.

# Using SBT

1. In a terminal, run the command:
  > sbt

This will open the sbt shell. From there, you can run the programs in your project.

2. Here are several useful commands when using the sbt shell:

> compile

* This command will compile all the files in the project you are in.

> run

* This command will display a list of all executables in the project. In the comand prompt, input the
index of the file to run.

> runMain (filename)

* This command will run the **Main** function in the file indicated.
* To run a program in a package, use the format **runMain packagename.mainName**


For example, to run `helloWorld`, the main function of the HelloWorld object located in
the directory `Examples`, input the following commands into the sbt shell:

>run
> (input the index of helloWorld)
>
or
>
> runMain helloWorld

Another useful trick is to use the `~` modification on any command. This modification
will make sbt continuously run whatever you put it in front of. Whenever there is a change to the files,
sbt will run the `~`'d command automatically.

> ~runMain helloWorld

This will automatically run helloWorld whenever there is a change to the file system.
Pressing enter into the command line will stop the automated command.

3. To exit the sbt shell, press **ctrl + d**

# Installing an IDE

## IntelliJ IDEA

1. Follow the instructions [here](https://www.jetbrains.com/help/idea/installation-guide.html)
   to install IntelliJ IDEA.

2. Download the [zipped code
   repository](https://github.com/EffectOrientedProgramming/book/Examples)
   and [unzip it](#unpacking-a-zip-archive).

3. Start IntelliJ IDEA, and select the `File | Open` menu item.  Navigate to
   where you unzipped the repository and open the `build.sbt` file.

4. Go to the menu and select:
   `View | Tool Windows | sbt`. Right-click the directory name, and reload the sbt project.
   This should ensure your machine has all necessary plugins and extensions installed.

## Visual Studio Code (VSCode)

TBD

