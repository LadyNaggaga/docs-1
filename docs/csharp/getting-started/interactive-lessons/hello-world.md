---
title: Hello World - C# Interactive Lessons | Microsoft Docs
description: Write your first C# program
keywords: C#, Get Started, Hello World, interactive, lesson
author: billwagner
ms.author: wiwagn
ms.date: 06/02/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
---

# Hello world lesson

You'll create your first C# program in this lesson. You'll learn the
structure of a C# program and the common elements that are part of every
C# program. You'll also learn the basic tools to manipulate text using
the C# programming language.

## Prerequisites

This lesson has no prerequisites.

## Hello world

Enter the following code into the code editor:

```csharp
using System;

namespace HelloWorld
{
    public class Program
    {
        public static void Main()
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Run this program, and you'll see the text `Hello World!`printed. Congratulations,
you've written you're first C# program.

## Understanding what you've created

Quite a few of the elements you'll use in every C# program are in this first
sample. These elements form the structure of C# programs. Let's examine them
before you move on to modifying this program. Rather than working line-by-line,
let's examine the building blocks from the inside out. This program, like all
programs, is made up of *statements*, *methods*, *classes*, and *namespaces*.

### statements

A *statement* is a line of code that does something.
Let's look at the line that writes the output:

```csharp
Console.WriteLine("Hello World!");
```

This *statement* calls a *method* named `WriteLine`. *Methods* are one of the
building blocks of C# programs. They are reusable blocks of code. In this
instance, the `WriteLine` method writes text output. 

Preceding the `WriteLine`, you see a *class* named `Console`. The `WriteLine`
method is a member of the `Console` class. Methods in C# are members of
a type, like a *class*.

The text "Hello World!" is a *parameter* that is passed to that method.
Methods take zero or more *parameters* that define information that will
be used in the method. The `WriteLine` method takes a text parameter for
the text that it will write.

At the end of that line is a semicolon. C# statements must end
with a semicolon.

### Methods

Next, let's look at the code surrounding that one line:

```csharp
public static void Main()
{
    Console.WriteLine("Hello World!");
}
```

You've written a *method* in your hello world program. That method is
named `Main`. Typically, the entry point to a C# program is a method
with the name `Main`. When you run your program, the `Main` method
executes. That calls the `WriteLine` method to write the text.

The *body* of the method is the code between the `{` and `}`
characters. In C#, curly braces define blocks of code, like
the statements in a method.

The *method signature* is the line `public static void Main()`. It defines
the name of the method, `Main`. The parentheses define the *parameters*
for the method. There is no text between the parentheses because this
method does not accept any parameters. The `public` keyword is an *access
modifier*. In this example, the method is public, meaning it can be called
from any code. In later lessons, you'll learn about limiting access to
methods. The `static` keyword defines this method as a *static method*.
Later lessons will expand on this topic. For now, let's just say that the
main entry point must be a `static` method.

Almost all of the code you write will be writing *methods*. Methods are
blocks of code that perform specific actions.

### Classes

Methods are contained in *classes*. You wrote a class named `Program`:

```csharp
public class Program
{
    public static void Main()
    {
        Console.WriteLine("Hello World!");
    }
}
```

You see more curly braces and similar keywords. The C# language
uses similar structure so that as you learn the language, you'll
learn symbols and concepts that make it easier to learn more of the language.

A *class* is defined using the `class` keyword, followed by the name. Preceding
the `class` keyword is the `public` keyword, an *access modifier* that says this
class can be used from any code. Like *methods* you place the members of a class
inside curly braces. In this example, you have placed one method inside the
`Program` class.

### namespaces

*Namespaces* are a way to organize code as programs grow largeer. You
might imagine that the larger a program gets, the more likely methods
or classes might accidentally have the same name. *Namespaces* provide
a further layer of organization. Here, you've placed all the code in
the `HelloWorld` namespace:

```csharp
namespace HelloWorld
```

Notice those familiar curly braces that define all the code you've placed
in the `HelloWorld` namespace.

The first line of the program shows how you can use code from another
*namespace*:

```csharp
using System;
```

A `using` statement says that you want to use classes and other types
defined in that namespace. Here, you want to use the types from the
`System` namespace. The `Console` class is defined in the `System`
namespace.

That's quite a few concepts for such a small program. Those concepts
help organize larger programs that you'll build with as you learn more
about the language. C# uses some of the same symbols and text for similar
concepts in many areas of the language. As you learn, you'll see new uses
for familiar symbols, making it easier to learn more quickly as you gain
experience.

## Declaring variables

Let's start modifying this program to do more for you. Instead of
just "Hello World!", let's make it say your name. Replace this line:

```csharp
Console.WriteLine("Hello World!");
```

with these lines, substituting your own name:

```csharp
string myName = "Bill Wagner";
var sayHello = "Hello " + myName;
Console.WriteLine(sayHello);
```

You've added a couple *variable declarations* in the code. The first line
declares the `myName` variable. The type is a `string`, which is a sequence
of text characters. The name `string` is used in many programming languages
for storing text. This variable is initialized when it is declared.

The next line also declares a variable, `sayHello`. This variable is declared
using the `var` keyword. It is also a `string`, even though it is declared
using `var`. This is an *implicitly typed variable*. Its type is determined
from the initial contents. The right side of the `=` is a string, so the
type of `sayHello` is a string.

This second assignment uses the familiar `+` symbol to concatenate `string`
variables. Let's run the code and see how it works.

## Working with the `String` class

Let's do more with the `string` variables. These variables are *objects*
of a *class*, the `String` class. The C# keyword `string` is a synonym
for the `System.String` class. A *class* is a type, and an *object*
represents an instance of that type. Each *class* defines useful methods
that you can use to work with instances of that type.

Let's explore a few of the methods defined in the `String` class. Make
changes to the code you've written so far by using the following members
of the `String` class:

The `ToUpper` method returns a new string that is the all capital letters
version of its parameter:

```csharp
var CAPITALS = sayHello.ToUpper();
```

Can you guess what would make a string all lower case? Try it.

You can replace some characters in a string using the `Replace` method:

```csharp
var sayGoodbye = sayHello.Replace("Hello", "Goodbye");
```

Try a fefw of these options yourself.

## String interpolation

Let's finish this first lesson with *string interpolation*. Some of the
most common activities for working with text are converting other variables
to text, and substituting that text into a string. It's so common that C#
built support into the language. Let's use it, and then explain how it works.

Add the following code to your program:

```csharp
Console.WriteLine($"{myName} started learning C# on {DateTime.Now}");
```

Run the code and see what happens.

The `$` indicates that the text that follows is a *format string* for an
*interpolated string*. In the format string, any text between `{` and `}`
represents an instance that should be replaced by its text representation.

The `{myName}` substitution replaces that text with the string variable
you declared for your name. The second substitution, `{DateTime.Now}`
uses another type, `DateTime`, and a property called `Now` that returns
the current date and time. That value is converted to text, and the
text is substituted.

We really don't need the time, and it might be off by hours
if you live in a different time zone from the server running your code.
You can use *format strings* to control how the text is generated. The
`DateTime` type uses the format string `D` to indicate that you only
want the date displayed. You put the format string inside the curly braces.
After the variable you want to display, add a `:` followed by the format
string, `D`.

```csharp
Console.WriteLine($"{myName} started learning C# on {DateTime.Now:D}");
```

Run it again, and you should see the date, instead of the full date and
time.

## Review

In this first lesson, you learned how C# programs are organized. You declare
*namespaces* that organize types that work together. You declare *classes*
that represent types and contain the code for your pgoram. You write *methods*
in those classes that perform the work for your program.

You explored one type, the `String` class, which is used to manipulate text.
You built strings, replaced content, and learned about *string interpolation*.

