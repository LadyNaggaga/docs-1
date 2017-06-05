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

# Welcome to C#

## Hello world

```csharp
 Console.WriteLine("Hello World!");
```
| [Output]()|
| --- | --- |
| Hello World !|

Congratulations, you've run you're first C# program.


## Declaring variables

Let's learn how to declare a variable.  Variables are declared using the `var` keyword.
| Example on declaring variables | 
| --- | --- |
```csharp
var name = "Sage";
```
**Using variables**
Now, let's us  use the variables.   Instead of saying  Sage, say your name instead.
| Editable Code | 
| --- | --- |
```csharp
var name = "Maria";
Console.WriteLine(name); 
```
| [Output]()|
| --- | --- |
| Hello Maria | 

## Working with  `Strings` 

A string is an object of type String whose value is text, and are contained in double quotation marks.

**Creating and Using Strings**
| Editable Code | 
| --- | --- |
```csharp
string myName = "Sage"; //declares a string variable
Console.WriteLine(myName);
```
| [Output]() |
| --- | --- |
| Sage | 


###String Methods
 Let's explore a few of the methods defined in the `String` class. 

**ToUpper**
The `ToUpper` method returns a new string that is the all capital letters

| Editable Code | 
| --- | --- |
```csharp
string myName = "sage";
Console.WriteLine(myName.ToUpper());
```
| [Out put ]()| 
| --- | --- |
|SAGE|

**Challenge**: Can you guess what would make a string all lower case? 
| Editable Code | 
| --- | --- |
```csharp
string myName = "SAGE";
//Hint Console.Writeline What?
```
|[ Out put]() | 
| --- | --- |
|Will appear here|

You can replace some characters in a string using the `Replace` method:
| Editable Code | 
| --- | --- |
```csharp
var sayHello = "Hello ";
var sayGoodbye = sayHello.Replace("Hello","Goodbye");
Console.WriteLine(sayGoodbye);
```
| [Out put]() | 
| --- | --- |
|Goodbye|

## String interpolation

You stick strings together using concatenation operator ` +` 
| Editable Code | 
| --- | --- |
```csharp
string myName = "Sage ";
var today = DateTime.Now; 
Console.WriteLine(myName +"started learning C# at "+ today);
```
And this would be the output  ` Sage started learning C# at 6/5/2017 10:02:20 PM`.

 Using concatenation  works however, there is another way you can do this and it's called *string interpolation*. 
 
| Editable Code | 
| --- | --- |
```csharp
string myName = "Sage ";
Console.WriteLine($"{myName} started learning C# on {DateTime.Now}");
```
| Out put | 
| --- | --- |
|Sage started learning C# on 6/5/2017 8:50:51 PM|



The `$` indicates that the text that follows is a *format string* for an
*interpolated string*. In the format string, any text between `{` and `}`
represents an instance that should be replaced by its text representation.

The `{myName}` substitution replaces that text with the string variable
you declared for your name. The second substitution, `{DateTime.Now}`
uses another type, `DateTime`, and a property called `Now` that returns
the current date and time. That value is converted to text, and the
text is substituted.

**Challenge:**Try to use *string interpolation* on the code below
| Editable Code | 
| --- | --- |
```csharp
string myName = "Sage ";
var today = DateTime.Now; //Hint do we need this line?
Console.WriteLine(myName +"started learning C#"+ today);
```
| [Out put]() | 
| --- | --- |
|Sage started learning C#6/5/2017 8:58:00 PM|



