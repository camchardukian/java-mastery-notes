# Intro

## Installing Java

JDK is short for _Java Development Kit_ which is basically a software development environment for building Java applications.

We can choose the latest release to have additional features available to us, or we can optimize for stability and support (as many Fortune 500 companies do) by choosing the latest long-term support release.

## Anatomy of a Java Program

When defining Java functions we start with the return type.

Each Java program should have a function called `main` which is the entry point to the program.

We can use classes as a container for related functions.

By convention we use _PascalCase_ for classes and _camelCase_ for methods.

## First Java Program

_Packages_ are used to group related classes.

All Java files should use the `.java` extension.

In Java we should always terminate statements with a semicolon.

The `main` method in our program should always be `static`.

## How Java Code Gets Executed

When we try to run a Java program we’ll basically go through two different steps: _Compilation_ and _Execution_.

The _Java Compiler_ compiles our source code into something called _bytecode_.

Java bytecode is platform-independent and can be executed on any machine that has a _Java Virtual Machine_ (JVM) installed (or a _Java Runtime Environment_ which would include the JVM as well as other necessary libraries and components)

The JVM converts the Java bytecode into the native code of the OS the JVM is running on top of (MacOS, Windows, etc).
