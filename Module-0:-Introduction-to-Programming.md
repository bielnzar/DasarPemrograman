## Table of Contents

- [IDE (Integrated Development Environment)](#ide-intregated-development-environment)

- [Introduction to the C Language](#introduction-to-the-c-language)

    + [Statement](#statement)
    + ["Hello, world."](#hello-world)
    + [Program Structure](#program-structure)
    + [Comments](#comments)

- [Keywords and Identifiers](#keywords-and-identifiers)

    + [Keywords](#keywords)
    + [Identifiers](#identifiers)

- [Variables](#variables)

    + [Introduction to Variables](#introduction-to-variables)
    + [Variable Declaration and Definition](#variable-declaration-and-definition)
    + [Assigning a Value](#assigning-a-value)
    + [Initializing a Variable](#initializing-a-variable)

- [Constants and Literals](#sonstants-and-literals)

    + [Constants and Literals](#constants-and-literals-1)
    + [Defining a Constant](#defining-a-constant)

- [Primary Data Types](#primary-data-types)

    + [Integer Type](#integer-type)
    + [Floating-point Type](#floating-point-type)
    + [Character Type](#character-type)

- [Basic Input and Output](#basic-input-and-output)

    + [Basic Output](#basic-output)
    + [Basic Input](#basic-input)

- [Operators](#operator)

    + [Assignment Operators](#operator-assignment)
    + [Arithmetic Operators](#operator-aritmatika)
    + [Increment and Decrement Operators](#operator-increment-dan-decrement)
    + [Relational Operators](#operator-relasional)
    + [Logical Operators](#operator-logika)
    + [Bitwise Operators](#operator-bitwise)
    + [Combined Operators](#operator-gabungan)
    + [Other Operators](#operator-lain)

# IDE (Integrated Development Environment)

Before we start coding, we need an IDE to simplify the coding process. What is an IDE? To put it simply, an IDE or Integrated Development Environment is a code editor application that also provides a compiler. Here are some IDEs for the C language that are commonly used:

- [DevC++](https://www.bloodshed.net/download.html)
- [CodeBlocks](http://www.codeblocks.org/downloads)

# Introduction to the C Language

## Statement

In a program, a **statement** is a command that instructs the computer to carry out a certain action, such as displaying something to the computer.

If we were to put it into an analogy, when we speak to someone, we use a language that we both understand, so that we can convey what we want to tell them. That's what a statement is. Conveying a message to someone is akin to a statement in a program.

## "Hello, world."

Let's start by creating a simple program, displaying the iconic sentence **"Hello, world!"** to the screen (console). This is the code for program:

```c
#include <stdio.h>  

int main()
{
    printf("Hello, world!\n");  
    return 0;  
}  
```

Copy the code above to your IDE, and then compile and run. The compilation process will result the following output.

```
Hello, world!
```

## Program Structure

To explain how the above program works, let's divide the code into several parts.

### Header File

The first line in the code is called the preprocessor directive. The preprocessor used in this case is '#include'

The '#include' preprocessor tells the preprocessor to insert the contents of another file, the **header file** `<stdio.h>` into the source code at the point where the #include directive is found. The `<stdio.h>` header file is a built-in C library that contains important functions needed by the program. In this case, the header file provides the 'printf()' function to display the sentence **“Hello, world!”**. Without the library, the program can't be compiled.

### `main()` Function

The `main()` function in the code is used from the 3rd line until the 7th line.

```c
int main()
{
    printf("Hello, world!\n");  
    return 0;  
}
```

In every C program, the `main()` function must always be there. This is because the execution of a code starts from the beginning of the `main()` function.

+ The 3rd line shows the name and the return type of the function. int is the type of _return_ for the function named `main()`. Then the symbol '{' denotes the start of the `main()` function
+ Line 4 through 6 contains the body of the `main()`function
+ Line 8 contains the symbol '}' which denotes the end of the `main()` function. Essentially, the body of a function will always be in-between the '{}' symbols.

### Whitespace

We can see that line 2 and 4 is empty (no characters whatsoever). This is called a **whitespace**. Whitespace is the empty area in a code, usually used to make the code more readable.

There are three kinds of whitespace, **space**, **tab**, and **new line**. Line 2 and 4 is an example of a new line whitespace.

### Statement

In the `main()` function, there are two **statements** in line 5 and line 6. Most statements ends with a semicolon (`;`).

```c
printf("Hello, world!\n");  
return 0;  
```

The statement in line 5 instructs the program to call the `printf()` function. The `printf()` function is a function provided in the library header `<stdio.h>` and is used to display an output to the console (screen). In this case, the `printf()` function receives a string argument **“Hello, world!\n”**. The `‘\n’` in the string is a special character used to print a new line.

While the statement in line 6 is called a return statement. The command `return 0` in the function `main()` is used to end the program and signalizes that the program has been successfully executed.

## Comments

**Comments** are a part of a program that will not be executed. Comments provide clarity to the C source code allowing others to better understand what the code was intended to accomplish and greatly helping in debugging the code. Comments are especially important in large projects containing hundreds or thousands of lines of source code or in projects in which many contributors are working on the source code. There are two types of comments in the C language.

### Single-Line Comments

As the name says, single-line comments only work in one line. Single-line comments start with the symbol `//`. All characters (in one line) starting with the symbol `//` will be ignored.
```c
// This is a single-line comment  
  
// Function to display to screen  
printf("HELLO\n");  

```

### Multi-Line Comments

While multi-line comments can span, well, multiple lines. (It can also just span a single line).  A multi-line comment will always start with `/*` and ends with `*/`. All characters between these two symbols will be ignored.
```c
/* 
This is a multi-line comment
Everything here will be ignored
borgars
*/  
```

[< Table of Contents](#table-of-contents)

# Keywords and Identifiers

## Keywords

Keywords are reserved words in a programming language that have their own distinctive meanings to a compiler. These words are part of syntaxes and cannot be used as identifiers.
Below is a list of keywords in C.

|               |           |           |           |
|---------------|:----------|:----------|:----------|
| auto          | double    | int       | struct    |
| break         | else      | long      | switch    |
| case          | enum      | register  | typedef   |
| char          | extern    | return    | union     |
| continue      | for       | signed    | void      |
| do            | if        | static    | while     |
| default       | goto      | sizeof    | volatile  |
| const         | float     | short     | unsigned  |

## Identifiers

Identifiers refer to the identification of an entity--variables, functions, structures, etc. Since it identifies an entity, it has to be unique (two entities cannot have the same identifier).

Identifier naming ruling:

+ Identifiers are not keywords.
+ Identifiers can only consist of lowercase letters, uppercase letters, digits, and the underscore symbol ( _ ).
+ Identifiers cannot contain a whitespace.
+ Identifiers has to start with a letter or the underscore symbol. They cannot start with a digit/number.
+ Identifiers are case-sensitive; the identifier `variable` is different from `vAriaBle`.

[< Table of Contents](#table-of-contents)

# Variables

## Introduction to Variables

A **variable** is a place to store modifiable data or value in the memory that can change as the program runs. in C language, variables store data/value with a specific type. An example is a variable that stores an integer type.

Variable can be analogized as a glass. In this case, the glass is what we call a **variable**. Glasses are commonly used to store liquids. So in this case, the liquids contained is called a **data type**. Subsequently, we can use water as an example of liquid, the **data** that is stored by the glass.
Basically, programs work by processing data. These data are then stored in variables.

## Variable Declaration and Definition

In C language, variables must be declared before use. Just like the case with glasses, there must exist a glass before it can be used.

To declare a variable, the syntax is as follows.

```
<data_type> <identifier>
```

For example, the following piece of code declares variable `x` with the type `int`.

```c
int x
```

If multiple variables of the same type are to be declared, the operator comma (`,`) can be used.

```
<data_type> <variable1>, <variable2>, ... etc;
```

```c
int x, y;
```

## Assigning a Value

After being declared, variables can be assigned a value. To do so, use the assignment operator (`=` symbol).

```
identifier_variabel = <corresponding value>
```

Example:

```c
int x, y;  
x = 10;  
y = -2; 
```

In this example, variables `x` and `y` each has a value of `10` and `-2`.

## Variable Initialization

The declaration and filling of variable values can be done in one instruction at a time. This is known as ** initialization **. By initializing the variable, it means that we give the variable an initial value.

```
data_type variable_identifier = <corresponding value>;
```

Example:

```c
int x = 10;
```

[< Table of Contents](#table-of-contents)

# Constants and Literals

## Constants and Literals

Constants refer to a value that cannot change or be modified, even by the program itself. Literals are constants whose values we explicitly define on code. For example:

```c
5       // Integer literal 
1.23    // Real number/floating point literal
'S'     // Character literal
"Hai"   // String literal 
```

Here are some types of literal in C.

| Type of Literal           | Example                       | Default  Type |
|---------------------------|:------------------------------|:--------------|
| Integer                   | `10, 0, -1 dll.`              | int           |
| Floating point            | `202.15, 33.24, -12.45 dll.`  | double        |
| Character                 | `‘A’, ‘1’, ‘#’`               | char          |
| String                    | `“Hai”`                       | const char[4] |

### Integer

There are three ways to write an integer literal: using decimal (10 base), octal (8 base), or hexadecimal (16 base) systems.
+ **Decimal** - most commonly used. Examples: `100, -22`.
+ **Octal** - starts with '0', followed by the octal number. Examples: `077, 033`.
+ **Hexadecimal** - starts with “0x”, followed by the hexadecimal number. Examples: `0x7f, 0x521`.

### Floating point (real number)

Floating point number is written by using the separator point (.) between the integer and the decimal figures. Examples: `2.321, -11.22, 0.00012`.

### Character

Character literals are enclosed with quotation marks (i.e. the character A is written by typing `‘A’`). Aside from normal characters, there are special characters in the C language that has particular functions. These characters cannot be written as is. For example, the character for a new line is represented by ‘\n’ and the backlash symbol with ‘\\’. Those characters are known as escape sequences. These are some escape sequences in C.

| Escape Sequence | Character           |
|-----------------|:--------------------|
| `\b`            | Backspace           |
| `\f`            | Form feed           |
| `\n`            | Newline             |
| `\r`            | Return              |
| `\t`            | Horizontal tab      |
| `\v`            | Vertical tab        |
| `\\`            | Backslash           |
| `\’`            | Quotation mark      |
| `\”`            | Double quot. mark   |
| `\?`            | Question mark       |
| `\0`            | Null character      |
| `\b`            | Backspace           |


### String

A string is a group of one or more characters. String literals are enclosed with double quotation marks. For instance, `“Hello, world.”`. Strings are represented by using arrays with type `char`. We'll get to this later.

## Defining A Constant

To define a constant, we can use these methods.

### Defining A Constant Variable

Values of variables in a program can be made constant to prevent them from being modified while the program is executing. This is done by adding a keyword `const` while defining that variable.
 
```c
const data_type var_name = <value of var_name>
```

Note that variable initialization needs to be done at the same time when defining a constant variable.
Example:

```c
const int    konstInt = 23;  
const double konstDouble = 23.12;
```

Every modification to constant variables will result in an error.

```c
const int konstInt = 23;  
konsInt = 11; // Error
```

### Using #define

Another way is to use the prepocessor directive `#define`. The syntax is as follows.
 
```
#define name <value of name>
```

Example:
```c
#define konstInt    23  
#define konstDouble 23.11  
  
int main()  
{  
    int    a = konstInt;  
    double b = konstDouble;  
}  
```
[< Table of Contents](#table-of-contents)

# Primary Data Types

A **data type** is the type and size of data. It determines what kind of data will be assigned to a variable (or an object in general).

There are several data types in C: primary, derivative, and void data types. For now we're going to focus on primary data types.

## Integer Type

An integer is a number with no fraction values. Integer data types in C are as follows.

<table>
    <thead>
        <tr>
            <th rowspan="2" align="center">Data Type</th>
            <th rowspan="2" align="center">Memory (in Bytes)</th>
            <th colspan="3" align="center">Value Range</th>
            <th rowspan="2" align="center">Format Specifier</th>
        </tr>
        <tr>
            <th align="center">Min</th>
            <th align="center"></th>
            <th align="center">Max</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>short</td>
            <td align="center">2</td>
            <td align="center">-2<sup>15</sup></td>
            <td align="center">s.d</td>
            <td align="center">2<sup>15</sup> - 1</td>
            <td align="center">%hi</td>
        </tr>
        <tr>
            <td>unsigned short</td>
            <td align="center">2 - 4</td>
            <td align="center">0</td>
            <td align="center">s.d</td>
            <td align="center">2<sup>16</sup> - 1</td>
            <td align="center">%hu</td>
        </tr>
        <tr>
            <td>int</td>
            <td align="center">4</td>
            <td align="center">-2<sup>31</sup></td>
            <td align="center">s.d</td>
            <td align="center">2<sup>31</sup> - 1</td>
            <td align="center">%d</td>
        </tr>
        <tr>
            <td>unsigned int</td>
            <td align="center">4</td>
            <td align="center">0</td>
            <td align="center">s.d</td>
            <td align="center">2<sup>32</sup> - 1</td>
            <td align="center">%u</td>
        </tr>
        <tr>
            <td>long</td>
            <td align="center">4</td>
            <td align="center">-2<sup>31</sup></td>
            <td align="center">s.d</td>
            <td align="center">2<sup>31</sup> - 1</td>
            <td align="center">%ld</td>
        </tr>
        <tr>
            <td>unsigned long</td>
            <td align="center">4</td>
            <td align="center">0</td>
            <td align="center">s.d</td>
            <td align="center">2<sup>32</sup> - 1</td>
            <td align="center">%lu</td>
        </tr>
        <tr>
            <td>long long</td>
            <td align="center">8</td>
            <td align="center">-2<sup>63</sup></td>
            <td align="center">s.d</td>
            <td align="center">2<sup>63</sup> - 1</td>
            <td align="center">%lld</td>
        </tr>
        <tr>
            <td>unisgned long long</td>
            <td align="center">8</td>
            <td align="center">0</td>
            <td align="center">s.d</td>
            <td align="center">2<sup>64</sup> - 1</td>
            <td align="center">%llu</td>
        </tr>
    </tbody>
</table>

Just like the name, the data types above are the ones used to represent integers (positive and negative) including the number 0, e.g. 0, -5, 12, -1, 200, etc. It can be seen from the table that there are two distinctive types of integers, namely **signed** and **unsigned**. **Signed integers** are able to be assigned negative integer values, while **unsigned integers** aren't. 

**It should be noted that** the data types above cannot be used to represent floatinf-point numbers (real numbers).

## Floating-point Type

Real numbers or floating-point numbers are numbers that have fraction values. Floating-point data types in C are as follows.

<table>
    <thead>
        <tr>
            <th align="center">Data Type</th>
            <th align="center">Memory (in Bytes)</th>
            <th align="center">Value Range</th>
            <th align="center">Format Specifier</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>float</td>
            <td align="center">4</td>
            <td align="center">&plusmn;3.4 x 10<sup>&plusmn;38</sup> (estimation)</td>
            <td align="center">%f</td>
        </tr>
        <tr>
            <td>double</td>
            <td align="center">8</td>
            <td align="center">&plusmn;1.7 x 10<sup>&plusmn;308</sup> (estimation)</td>
            <td align="center">%lf</td>
        </tr>
    </tbody>
</table>

The data types above are used to store floating-point or decimal values, e.g. `2.35, -12.246, 0.005` etc.

## Character Type

Characters in C are actually integers, meaning: every character has its own code, called ASCII, which can be represented as an integer.

<table>
    <thead>
        <tr>
            <th align="center">Data Type</th>
            <th align="center">Memory (Bytes)</th>
            <th align="center">Value Range</th>
            <th align="center">Format Specifier</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>char</td>
            <td align="center">1</td>
            <td align="center">-2<sup>7</sup> s.d 2<sup>7</sup> - 1</td>
            <td align="center">%c</td>
        </tr>
        <tr>
            <td>unsigned char</td>
            <td align="center">1</td>
            <td align="center">0 s.d 2<sup>8</sup> - 1</td>
            <td align="center">%c</td>
        </tr>
    </tbody>
</table>

The data types above are most commly used to represent a single character, e.g. `‘A’`, `‘-‘`, etc.

[< Table of Contents](#table-of-contents)

# Basic Input and Output

Interactivity can be added to programs that we make. We can instruct them to receive input (from keyboard) and then display the output (on the console, displayed on monitor). Functions that enable input and output reside in the library `<stdio.h>` (standard input output).

## Basic Output

### Print Function `printf()`

To print the output on to the console, we need to use the function `printf()`. As we have known, this function takes in a string as an argument.

```c
#include <stdio.h>  
  
int main()   
{  
    printf("This is a string\n");  
    return 0;  
} 
```

Output

```
This is a string
```

We can add an escape sequence to a string. For instance, by changing the statement `printf()` above to:

```c
printf("This is a string\nI am a new-line\n\tI am the character \\tab");
```  
 
```
This is a string
I am a new-line
    I am the character \tab
```

Separating two `printf()` statements on different lines doesn't mean printing the strings on different lines as well.

```c
#include <stdio.h>  
  
int main()   
{  
    printf("Did you think I was going to");  
    printf("Move to a new line?");  
    return 0;  
}  
```

Output

```
Did you think I was going toMove to a new line?
```

The code snippets above are examples on how to print constant strings. Then what if we wanted to print a string altogether with another variable's value, or print the values of a combination of two or more different variables?


### Output with Format Specifier

To print a value of a variable, we need to insert an additional argument inside the function `printf()`. The first argument inside `printf()` is always a string. We can insert as many variables as needed as the second, third or more arguments.
Do remember that in chapter [Primary Data Types](#primary-data-types), **every data type has its own format specifier**. This format specifier is what we're going to use to print the value of a variable.
 
```
printf(“<format string>”, var1, var2, var3, ... dst);
```

For instance, let's say we have two variables of types int and char, which are `a = 2` and `b = ‘X’`. We want to print the values of a and be separated by a whitespace. The program will look like this:

```c
#include <stdio.h>  
  
int main()   
{  
    int  a = 2;  
    char b = 'X';  
    printf("%d %c", a, b);  
    return 0;  
}
```

Output

```
2 X
```
 
See the illustration below.
 
![a](https://github.com/AlproITS/DasarPemrograman/blob/master/img/pict_printf.png)

By including matching format specifiers, we can print the value of a variable. 
+ The `printf()` function above prints a string containing two variable values (two format specifiers separated by a space).
+ The first format specifier is of data type int and refers to the first variable, which is a.
+ The second format specifier is of data type char and refers to the second variable, which is b.
+ So on and so forth, one format specifier for one variable consecutively.
Thus, we can print a string together with multiple values by including corresponding format specifiers.

```c
printf("Nilai dari a = %d, dan b = '%c'", a, b);    
```

```
Nilai dari a = 2, dan b = ‘X’
```

## Basic Input

### Scan Function `scanf()`

In common, input is used to receive data or values from a user. Then, that data or value will be assigned to a variable which will be processed afterward.
To execute input from keyboard, the function we need to use is `scanf()`. The parameters of this function is exactly the same as that of `printf()`'s. We use format specifiers to determine the data type of our input, then that data will be assigned to a variable.

Example:

The program below receives an integer input which is stored in the variable n, then prints its value with the format _“n has value = n”_.

```c
#include <stdio.h>  
  
int main()   
{  
    int n;  
    scanf("%d", &n);  
    printf("n has value = %d", n);  
    return 0;  
} 
```

Input

```
3
```

Output

```
n has value = 3
```
[< Table of Contents](#table-of-contents)

# Operators

An **operator** can be understood as something that does an operation to operands. For instance, the operator + is used for additions.

Based on the amount of operands enclosing an operator, operators are categorized into three.

+ **Unary** – operators that perform on **one** operand, e.g. -5.
+ **Binary** – operators that perform on **two**operands, e.g. 2 + 3.
+ **Ternary** – operators that perform on **three** operands (will be discussed later).

Meanwhile, based on functionality, operators in C are as follows.

## Assignment Operators

**Assignment operators** are used to assign a value to a variable. It is represented by the equal symbol `=`. Examples:

```c
int x, y;  
x = 4;  
y = 3;  
x = x + y; // x = 7  
y = x + x; // y = 14 
```

## Arithmetic Operators

Just like its name, an **arithmetic operator** performs mathematical operations such as addition, subtraction, division, etc. Some of these operators in C are represented with the same symbols as the ones normally used (addition uses `‘+’`, subtraction uses `‘-‘`, etc. Here is a list of arithmetic operators in C:

| Symbol | Operation                                                                    | Example  |
|:------:| ---------------------------------------------------------------------------- | :------: |
| +      | Addition of two operands                                                     | `a + b`  |
| -      | Subtraction of two operands                                                  | `a - b`  |
| *      | Multiplication of two operands                                               | `a * b`  |
| /      | Division of two operands                                                     | `a / b`  |
| %      | Calculates the remainder of the division of two operands (modulo operation)  | `a % b`  |

## Increment and Decrement Operators

Operator `++` is called an **increment** operator, meanwhile operator `--` is a **decrement** operator. Both of these operators are used to increase or decrease the value of a variablye by 1.

There are two ways to use these operators.

+ **Prefix** - putting an increment/decrement operator before the name of the variable. 

    ```c
    int a, b;  
    a = 5;  
    ++a; // a is now 6  
    --a; // a is now 5
    ```

    How the prefix way works is by increasing/decreasing the operand (value of a variable) before the operand is used on other operations in the same instruction sequence. Let's see the code snippet below:

    ```c
    int a, b;  
    a = 5;  
    b = ++a; // b is now 6  
    a = --b; // a is now 5 
    ```

    Here, when the instruction sequence `b = ++a;` is being executed, what happens first is that the value of `a` is incremented by 1, then it is assigned to the variable `b`. Try it yourself!


+ **Postfix** - putting an increment/decrement operator after the name of the variable. Here, the operand (value of a variable) will be incremented/decremented by 1 after it is used on other operations in the same instruction sequence. Let's take a look:

    ```c
    int a, b;  
    a = 5;  
    b = a++; // b is now 5  
    a = b--; // a is now 5 
    ```

    Here, when the instruction sequence `b = a++;` is being executed, what happens is that the value of `a` will be assigned to the variable `b` first, and then be incremented by 1. Hence, the value of `b` is the same as the initial value of `a`.

## Relational Operators

**Relational operators** are used to check the relations of two operands and compare their values. If both operands are the same, the comparation results in a **TRUE** value (represented by the number 1), otherwise it results in a **FALSE** value (represented by the number 0).

Here is a list of relational operators in C.

| Operator                 | Symbol   | Details                                                                                               | Example                                           |
| ------------------------ | :----:   | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Equality                 | ==       | Used to check whether two operands have the same value.                                               | 5 == 2 (FALSE)<br>5 == 5 (TRUE)                  |
| Inequality               | !=       | Used to check whether two operands have different values.                                             | 5 != 2 (TRUE)<br>5 != 5 (FALSE)                  |
| Greater than             | >        | Used to check whether first operand is greater than second operand.                                   | 5 > 2 (TRUE)<br>5 > 5 (FALSE)<br>2 > 4 (FALSE)   |
| Less than                | <        | Used to check whether first operand is less than second operand.                                      | 5 < 2 (FALSE)<br>5 < 5 (FALSE)<br>2 < 4 (TRUE)   |
| Greater than or equal to | >=       | Used to check whether first operand is greater than or equal to second operand.                       | 5 >= 2 (TRUE)<br>5 >= 5 (TRUE)<br>2 >= 4 (FALSE) |
| Less than or equal to    | <=       | Used to check whether first operand is less than or equal to second operand.                          | 5 <= 2 (FALSE)<br>5 <= 5 (TRUE)<br>2 <= 4 (TRUE) |

## Logical Operators

**Logical operators** are used to check on conditions/expressions, whether a condition is correct or incorrect. Logical operators only results in either a **TRUE** value (if condition is correct, represented by the number 1) or **FALSE** value (if condition is incorrect, represented by the number 0).
Operator-operator logika dalam bahasa C adalah sebagai berikut.

| Operator                | Symbol   | Details                                                                                               | Truth value                                                      |
| ----------------------- |:------:  | ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Logical NOT             | !        | NOT operator is used to invert the evaluation of a condition, TRUE becomes FALSE and vice versa.      | `!1 = 0`<br>`!0 = 1`                                             |
| Logical AND             | &&       | AND operator will result in TRUE if both operands are equivalent to TRUE.                             | `1 && 1 = 1`<br>`0 && 1 = 0`<br>`1 && 0 = 0`<br>`0 && 0 = 0`         |
| Logical OR              | \|\|     | OR operator will result in TRUE if one or more operand is equivalent to the value of TRUE.            | `1 \|\| 1 = 1`<br>`0 \|\| 1 = 1`<br>`1 \|\| 0 = 1`<br>`0 \|\| 0 = 0` |

> The logical operator **NOT** is a unary operator which means it will only work on a single operand.

Logical operators are commonly used together with relational operators to be used in expression/condition evaluations, which is to test the truth or correctness of a condition. You will find a lot of these in branching (which we'll talk more about in a later module).

Example:

```c
int a, b, c, d;  
a = 11;  
b = 24;  
c = 11;  
d = ((a == c) && (b > a));               // 1 (TRUE)  
d = ((a >= b) || (a < c));               // 0 (FALSE)  
d = ((b != b) || (b > c)) && (c == a);   // 1 (TRUE) 
```

## Bitwise Operators

**Bitwise operators**, like the name, are used to perform operations on two operands in a binary scale (base 2 numbers). Before learning further about how bitwise operations work, it's better that we understand binary numbers.

There are 6 bitwise operators: **AND**, **OR**, **XOR**, **COMPELEMENT**, **SHIFT LEFT**, and **SHIFT RIGHT**. Let's look at the table below to understand their differences.

| Operator                | Symbol | Details                                                                                                                             |
| ----------------------- | :----: | -------------------------------------------------------------------------------------------------------------------------------------- |
| Bitwise AND             | &      | Evaluates two operands per bit. Results in 1 if both operand bits are 1, otherwise results in 0.               |
| Bitwise OR              | \|     | Evaluates two operands per bit. Results in 1 if one or more operand bits are 1, otherwise results in 0.        |
| Bitwise XOR             | ^      | Evaluates two operands per bit. Results in 1 if both operand bits are different, otherwise results in 0.       |
| Bitwise COMPLEMENT      | ~      | Inverses all bit values, 1 to 0 and 0 to 1 (in bit length).                                                    |
| Bitwise SHIFT LEFT      | <<     | Shift bits to the left for as many as n (second operand).                                                                                       |
| Bitwise SHIFT RIGHT     | >>     | Shift bits to the right for as many as n (second operand).                                                                                      |

**Bitwise operators examples:**

Suppose we have the numbers 12 and 5. In binary, 12 is represented as (1100) and 5 as (0101). The bitwise operations for these numbers are as follows.

+ **Bitwise AND**

    ```
    12 = (1100)
     5 = (0101)
    ------------ &
     4 = (0100)
    ```

+ **Bitwise OR**

    ```
    12 = (1100)
     5 = (0101)
    ------------ | 
    13 = (1101)
    ```

+ **Bitwise XOR**

    ```
    12 = (1100)
     5 = (0101)
    ------------ ^
     9 = (1001)
    ```

+ **Bitwise COMPLEMENT**

    ```
     12 = (1100)
    ~12 = (0011)
    ```

+ **Bitwise SHIFT LEFT**

    Suppose we want to shift the bits of 13 to the left as many as 2, then the expression is 13 << 2.

    ```
         13 = (001101)
    13 << 2 = (110100) 
    ```

    Notice that the rightmost bit, after the left shifts, will be filled with 0's. Therefore the result of 13 << 2 = 52.

+ **Bitwise SHIFT RIGHT**

    Now, suppose we want to shift the bits of 13 to the right as many as 2, then the expression is 13 >> 2.

    ```
         13 = (001101)
    13 >> 2 = (000011)
    ```

    Notice that the leftmost bit, after the right shifts, will be filled with 0's. Therefore the result of 13 >> 2 = 3.

## Compound Operators

A **compound operator** is a combination of two operators. These are used to shorten code writing. Here is a list of compound operators in C.

| Operator | Example   | Equivalent with         |
| :------: | :------:  | :---------------------: |
| +=	   | `a += b`  |	`a = a + b`      |
| -=	   | `a -= b`  |	`a = a - b`      |
| *=	   | `a *= b`  |	`a = a * b`      |
| /=	   | `a /= b`  |	`a = a / b`      |
| %=	   | `a %= b`  |	`a = a % b`      |
| &=	   | `a &= b`  |	`a = a & b`      |
| \|=	   | `a \|= b` |	`a = a \| b`     |
| ^=	   | `a ^= b`  |	`a = a ^ b`      |
| >>=	   | `a >>= b` |	`a = a >> b`     |
| <<=	   | `a <<= b` |	`a = a << b`     |

## Other Operators

Aside from the operators explained above, there are other operators we can find in C.

### `sizeof()` Operator

Although its form is more similar to a function, in the standardization of the C programming language it is an operator. The use of this operator is to find out the size of memory allocated by an operand (can be a variable or a data type) in bytes.

Example:

```c
sizeof(int);
```

### Address-of Operator (`&`)

This operators returns the memory address of an operand (variable).

Example:

```c
int var;
scanf("%d\n", &var);
```

### Dereference Operator (`*`)

Contrary to the address-of operator (`&`), dereference operator (`*`) returns the value of a pointer variable (this will be further explained in a later module on Pointers).

> Although it uses the same symbol as a multiplier, dereference operator has a totally different function than the multiplier.

### Conditional Operator (` ? : `)

Conditional operator is the only ternary operator (works on three operands) in C. Its function is similar to `if - else` statement (will be further explained in a later module on Branching).

### Comma Operator (`,`)

The comma operator (`,`) in C is used as a binary operator when used in the same sequence as assignment. It will only consider the rightmost operand as the value to be assigned.

```c
int number = (5, 23);   // number is equal to 23, not 5
```

Aside from functioning as an operator, the comma sign (`,`) is also used as a separator between statements. For instance when making declarations of more than one variable.

```c
int var1, var2, var3;   
// Usage of the comma sign to separate the declaration of each variable
```

> Not all statements can be separated by the comma sign.

### Subscript Operator (`[]`)

It is most commonly used to access an array element (will be explained in a later module on Arrays).

_Other operators not discussed in this module will be explained in later modules._

[< Table of Contents](#table-of-contents)
