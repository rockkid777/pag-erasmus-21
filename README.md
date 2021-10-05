# Brief Introduction to The Magical Realm of Programming

This document is created as a handout of my workshop at Péter András Gimnázium
for Erasmus high school teachers. The aim is to get a grasp of basic programming
concepts in a trending paradigm and technology stack what they could pass on
to their students across many countries in Europe.

## Table of Contents

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
	- [Short History of Computer Science](#short-history-of-computer-science)
	- [Programming Languages](#programming-languages)
	- [Programming Language Categories](#programming-language-categories)
- [Learn Concepts By Examples](#learn-concepts-by-examples)
	- [Hello World!](#hello-world)
	- [Flow Controll](#flow-controll)
		- [Variables](#variables)
		- [Sequence of Statements](#sequence-of-statements)
			- [Excercise: Greetings](#excercise-greetings)
		- [Alternatives](#alternatives)
			- [Excercise: even or odd?](#excercise-even-or-odd)
		- [Loops](#loops)
		- [Excercise: What Number Am I Thinking About?](#excercise-what-number-am-i-thinking-about)
	- [Functions and Procedures](#functions-and-procedures)
		- [Excercises: Structure your code!](#excercises-structure-your-code)
	- [Object Oriented Programming](#object-oriented-programming)
		- [Objects and Classes](#objects-and-classes)
		- [Encapsulation](#encapsulation)
			- [Excercise: Guess Game Manager](#excercise-guess-game-manager)
		- [Polymorphism and Interfaces](#polymorphism-and-interfaces)
			- [Excercise: Car Interface with DieselCar and ElecricCar Classes](#excercise-car-interface-with-dieselcar-and-elecriccar-classes)
- [Applications With Graphical User Interfaces](#applications-with-graphical-user-interfaces)
	- [Event-Based Applications](#event-based-applications)
	- [Catch My Button!](#catch-my-button)
	- [What Number Am I Thinking About?](#what-number-am-i-thinking-about)
	- [Evaluate My Homework!](#evaluate-my-homework)
	- [Memory Game](#memory-game)

<!-- /TOC -->

## Introduction

### Short History of Computer Science

One of the first computer science models is Alan Turing's "automatic machine",
lately called ["Turing machine"][turing-machine] (by Alonzo Church). These machines operate with
sequentially readable and writable machine tapes. The machines themselves
represent their programs, their "configurations". These configurations define
state transitions on certain inputs (read from tape).

The next big iteration is the Random Access Machine (RAM machines) which uses
registers instead of tapes. Harvard architecture stores program and data
separated, while John von Neumann, Hungarian mathematician created his
architecture as a review of EDVAC. His architecture stores both program and data
in RAM memory, this is the so-called stored-program principle on which computers
(including smartphones, smart watches, smart refrigerators, etc) we have Today
are based on.

### Programming Languages

At first, programmers wrote machine codes directly, actual sequences of ones
and zeroes, which had proven to be hard to read by human eyes, and easy to make
mistakes in. This situation generated the demand for new tools for programming
computers -- generating machine code -- which helps association.

**Assembly** is a programming language which eases association between source
code -- created by programmers -- and actual machine code which is to be
executed. Assembly directly maps machine (CPU) instructions and register names.
An Assembly compiler -- which creates machine code from source code written in
Assembly language -- is called an assembler. The following snippet stores
integer number 5 and 7 in registry eax and ebx, then calculates their sum,
stored in eax.

``` assembly
mov eax 5
mov ebx 7
add eax ebx
```

Programming languages which introduce further abstractions -- diverging from 1:1
representation of CPU command set -- are called higher-order programming
languages.

### Programming Language Categories

Programming languages can be categorised in multiple ways by multiple properties
like paradigms, support of different language constructions, but one of the main
dividers is the fact if they are compiled languages or interpreted ones?

**Compiled languages** are using compilers to generate executable programs.
Compiled languages tend to be strictly-typed, and in general, their executables
have better performance than interpreted languages, implementing the same
computations. Few example of compiled languages: C, C++, Fortran, Swift.

**Interpreted languages** are using interpreters to execute source code (text
form) written in their programming language. Interpreters work by interpreting
source code line-by-line as execution goes. Interpreted languages are useful
because their portability and ease of modification, this is why it is popular
among scripting languages, like Bash, Python, JavaScript.

Interesting fact about JavaScript: It has been born to be interpreted
by web browsers, handling dynamic content and basic interactions. Today all
mainstream web browsers support JavaScript as part of their base functionality.
JavaScript is actively developed with it's standard, ECMAScript, by it's
standard committee. JavaScript lives it's renaissance with the emerge of single
page web applications, such as Facebook (the webpage), Twitter, even Microsoft
Teams and GMail, Google Hangouts, etc.

**Hybrids** are those programming languages which can be both interpreted and
compiled as well. Such language is Haskell, a pure functional programming
language. Another type of Hybrid languages are those languages which are
being compiled not directly into machine code (binary), but into so-called
"byte code", which by itself cannot be executed, only interpretable by
Vritual Machines. These Virtual machines, like Java Virtual Machine or .Net
Frameworks exist to serve as a layer between their own type of byte code and
the virtual machine itself. These virtual machines are implemented on multiple
Operating Systems on multiple hardware architectures, so a source code compiled
only once, can be executed on multiple environments. These languages take
benefits of having their compiler (static analysis, strong type-systems,
optimalisation) and the portability of interpreted languages. Their
performance is somewhere in between the 2 main category. Their byte code is
generated for the VM itself, uses lower-level abstractions then the source
language, using VM command set, and easier to parse).

## Learn Concepts By Examples

Our programming language of choice in the following sections is C#, because
it introduces the basics for beginners in a type-safe environment, while
supports most of the modern program language concepts for those who
are willing to learn how to express their computations in more expressive
and safe ways. Also C# is used widely in the industry from web services, mobile
applications through artificial intelligence to game developments. Available
on multiple platforms. However, for our graphical application examples later on
Windows is a requirement. With a bit of learning other frameworks (like
Xamarin) can be used to achieve the same results on them.
Choice is made respecting availability of Windows in classrooms across Europe.

### Hello World!

Let's create our first commandline application in Visual Studio:

1. Start Visual Studio
2. Click New Console Application
3. Name it "Hello World" and save it
4. Click "Build and run"

### Flow Controll

#### Variables

Since the whole architecture of computers and the bases of computer science are
born of Turing Machines, and by their "step-by-step" analogy, the most trending
paradigm is imperative paradigm when we discuss algorithms at their core
concepts. Imperative style uses the term "state" which by name refers to the
state of the computer, or in our case the program. A single dimensional
projection of state is a **variable**, which stores a single value. On the other
way around our initial (and adequate on introduction level) definition of
**state** is the conjunction of all of our variables with their values in the
moment of observing.

#### Sequence of Statements

C# combines statements into sequences by listing commands. Each command is
terminated with a semicolon.

``` C#
Console.WriteLine("Hello!");
Console.WriteLine("How are you?");
```

##### Excercise: Greetings

1. Create a program, which declares a string variable,
2. Ask users name, (awaits input to variable)
3. Greets user by name

#### Alternatives

With the introduction of "if" (conditional execution) C# is able to handle
alternatives.

Forms of if

``` Csharp
int a = 6;
if (a < 4) {
	Console.WriteLine("a is lesser than 4");
}
Console.WriteLine("Hello!");
```

If-Else

``` Csharp
int a = 6;
if (a < 4) {
	Console.WriteLine("a is lesser than 4");
} else {
	Console.WriteLine("a is greater or equal than 4");
}
Console.WriteLine("Hello!");
```

Else-If

``` Csharp
int a = 6;
if (a < 4) {
	Console.WriteLine("a is lesser than 4");
} else if (a == 4) {
	Console.WriteLine("a equals 4");
} else {
	Console.WriteLine("a is greater than 4");
}
Console.WriteLine("Hello!");
```

##### Excercise: even or odd?

1. Create a program which tells if given integer input is equal.
2. Create the same program using different if structure.

#### Loops

For "counter" loop

``` Csharp
for (int i = 0; i < 5; i++)
{
  Console.WriteLine(i);
}
```

While "pre-tester" loop

Note: A a post-tester alternative, do-while can be used.

``` Csharp
int i = 0;
while (i < 5)
{
  Console.WriteLine(i);
  i++;
}
```

#### Excercise: What Number Am I Thinking About?

Write a program which reads input until guess is correct

Note: Binary search or half-interval can be introduced with this example.

### Functions and Procedures

#### Excercises: Structure your code!

Structure your previous solutions into functions and procedures.

When to use functions? When to use procedures?

### Object Oriented Programming

#### Objects and Classes

#### Encapsulation

##### Excercise: Guess Game Manager

Create a guess game manager with private stored number and public CheckGuess
logical function.

#### Polymorphism and Interfaces

##### Excercise: Car Interface with DieselCar and ElecricCar Classes

Create Car interface with

- TopSpeed property
- Start procesure
- Stop procedure
- Accelerate procedure
- Brake procedure

Implement Car interface with DieselCar and ElectricCar classes

## Applications With Graphical User Interfaces

### Event-Based Applications

### Catch My Button!

Create GUI application with a single  button which "jumps" to other position
on mouse hover.

### What Number Am I Thinking About?

Implement the same guess game as a GUI app, using text box and buttons
and labels.

Note: guess game manager is reusable on this excercise.

### Evaluate My Homework!

Create an application which can calculate speed, distance and time (in case
two of them is already given).

### Memory Game

Generate an n times m game board of buttons, implement the classic memory game!


[turing-machine]: https://en.wikipedia.org/wiki/Turing_machine
