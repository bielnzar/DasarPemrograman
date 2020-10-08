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
 
![Oi ini nanti gambar](/img/pict_printf.png)

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

# Operator

**Operator** dapat dipahami sebagai sesuatu yang dapat melakukan operasi pada operan (variabel/nilai). Contohnya, operator + digunakan untuk operasi penjumlahan.

Dilihat dari jumlah operannya, operator dibagi menjadi tiga jenis, yaitu:

+ **Unary** – yakni operator yang bekerja pada satu operan, misalnya -5.
+ **Binary** – yakni operator yang bekerja pada dua operan, misalnya 2 + 3.
+ **Ternary** – yakni operator yang bekerja pada tiga operan. (Akan dibahas pada bagian selanjutnya).

Dilihat dari kegunaannya, berikut adalah jenis-jenis operator pada bahasa C.

## Operator Assignment

**Operator Assignment** digunakan untuk mengisikan (assign) sebuah nilai ke variabel. Simbol yang biasa digunakan adalah tanda sama dengan  `=`. Contohnya:

```c
int x, y;  
x = 4;  
y = 3;  
x = x + y; // x = 7  
y = x + x; // y = 14 
```

## Operator Aritmatika

Seperti namanya, **operator aritmatika** melakukan operasi layaknya pada matematika seperti penjumlahan, pengurangan, pembagian dsb. Beberapa operator menggunakan simbol yang sama pada matematika (penjumlahan dengan simbol `‘+’`, pengurangan dengan `‘-‘`, dst.). Operator-operator aritmatika pada bahasa C adalah sebagai berikut.

| Simbol | Operasi                                               | Contoh   |
|:------:| ----------------------------------------------------- | :------: |
| +      | Penjumlahan pada dua operan                           | `a + b`  |
| -      | Pengurangan pada dua operan                           | `a - b`  |
| *      | Perkalian pada dua operan                             | `a * b`  |
| /      | Pembagian pada dua operan                             | `a / b`  |
| %      | Menghitung sisa pembagian dua operan (operasi modulo) | `a % b`  |

## Operator Increment dan Decrement

Operator `++` disebut dengan operator **increment**, sedangkan operator `--` merupakan operator **decrement**. Kedua operator ini digunakan untuk menambah (increment)/mengurangi (decrement) nilai dari suatu variabel sebanyak satu.

Terdapat dua cara untuk menggunakan operator ini.

+ **Prefix** - yakni dengan meletakkan operator increment/decrement didepan nama variabel. 

    ```c
    int a, b;  
    a = 5;  
    ++a; // Nilai a sekarang adalah 6  
    --a; // Nilai a sekarang adalah 5
    ```

    Cara kerja dari operator increment/decrement prefix adalah dengan menambahkan/mengurangi nilai variabel sebanyak satu terlebih dahulu, sebelum operan tersebut digunakan pada operasi lainnya pada sekuens intstruksi yang sama. Untuk lebih jelasnya, perhatikan potongan kode berikut

    ```c
    int a, b;  
    a = 5;  
    b = ++a; // Nilai b sekarang adalah 6  
    a = --b; // Nilai a sekarang adalah 5 
    ```

    Di sini, saat instruksi `b = ++a;` dieksekusi, yang terjadi pertama kali adalah nilai dari `a` ditambahkan satu terlebih dahulu, kemudian baru di-assign nilainya ke variabel `b`.

+ **Postfix** - yakni dengan meletakkan operator increment/decrement di belakang nama variabel. Cara kerja dari operator increment/decrement postfix berbeda dari prefix. Pada postfix, nilai variabel akan ditambah satu setelah operan digunakan pada operasi lainnya pada sekuens instruksi yang sama. Perhatikan potongan kode berikut.

    ```c
    int a, b;  
    a = 5;  
    b = a++; // Nilai b sekarang adalah 5  
    a = b--; // Nilai a sekarang adalah 5 
    ```

    Di sini, saat instruksi `b = a++;` dieksekusi, yang terjadi pertama kali adalah nilai dari `a` akan di-assign terlebih dahulu ke variabel `b`, kemudian baru ditambahkan satu. Karena itulah variabel `b` mendapat nilai dari `a` sebelum terjadi penambahan.

## Operator Relasional

**Operator Relasional** digunakan untuk memeriksa relasi dan membandingkan nilai dari dua operan. Jika benar akan menghasilkan nilai **TRUE** (direpresentasikan angka 1), jika salah maka akan menghasilkan nilai **FALSE** (direpresentasikan angka 0).

Berikut adalah operator relasional dalam bahasa C.

| Operator                | Simbol   | Keterangan                                                                                            | Contoh                                           |
| ----------------------- | :----:   | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Sama dengan             | ==       | Digunakan untuk memeriksa apakah kedua operan memiliki nilai yang sama.                               | 5 == 2 (FALSE)<br>5 == 5 (TRUE)                  |
| Tidak Sama dengan       | !=       | Digunakan untuk memeriksa apakah kedua operan memiliki nilai yang tidak sama.                         | 5 != 2 (TRUE)<br>5 != 5 (FALSE)                  |
| Lebih besar             | >        | Digunakan untuk membandingkan apakah operan pertama lebih besar nilainya dari operan kedua.           | 5 > 2 (TRUE)<br>5 > 5 (FALSE)<br>2 > 4 (FALSE)   |
| Lebih kecil             | <        | Digunakan untuk membandingkan apakah operan pertama lebih kecil nilainya dari operan kedua.           | 5 < 2 (FALSE)<br>5 < 5 (FALSE)<br>2 < 4 (TRUE)   |
| Lebih besar sama dengan | >=       | Digunakan untuk membandingkan apakah operan pertama lebih besar atau sama nilainya dari operan kedua. | 5 >= 2 (TRUE)<br>5 >= 5 (TRUE)<br>2 >= 4 (FALSE) |
| Lebih kecil sama dengan | <=       | Digunakan untuk membandingkan apakah operan pertama lebih kecil atau sama nilainya dari operan kedua. | 5 <= 2 (FALSE)<br>5 <= 5 (TRUE)<br>2 <= 4 (TRUE) |

## Operator Logika

**Operator Logika** digunakan untuk melakukan tes pada kondisi/ekspresi, apakah kondisi tersebut benar atau salah. Operator logika hanya akan menghasilkan nilai **TRUE** (jika benar) atau **FALSE** (jika salah). TRUE direpresentasikan oleh angka 1, sedangkan FALSE oleh angka 0.

Operator-operator logika dalam bahasa C adalah sebagai berikut.

| Operator                | Simbol   | Keterangan                                                                                            | Nilai Kebenaran                                              |
| ----------------------- |:------:  | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Logical NOT             | !        | Operator NOT digunakan untuk membalikkan kondisi, TRUE menjadi FALSE dan FALSE menjadi TRUE.          | `!1 = 0`<br>`!0 = 1`                                         |
| Logical AND             | &&       | Operator AND akan menghasilkan nilai TRUE jika kedua operan mempunyai nilai TRUE.                     | `1 && 1 = 1`<br>`0 && 1 = 0`<br>`1 && 0 = 0`<br>`0 && 0 = 0` |
| Logical OR              | \|\|      | Operator OR akan menghasilkan nilai TRUE jika salah satu operan mempunyai nilai TRUE.                | `1 \|\| 1 = 1`<br>`0 \|\| 1 = 1`<br>`1 \|\| 0 = 1`<br>`0 \|\| 0 = 0` |

> Operator Logika **NOT** merupakan operator unary yang artinya hanya pada bekerja pada satu operan

Operator logika pada umumnya digunakan bersamaan dengan operator relasional untuk melakukan tes pada ekspresi yang berhubungan dengan kebenaran suatu kondisi. Penggunaan paling umum adalah untuk melakukan percabangan (akan dipelajari di bagian selanjutnya).

Contoh:

```c
int a, b, c, d;  
a = 11;  
b = 24;  
c = 11;  
d = ((a == c) && (b > a));               // 1 (TRUE)  
d = ((a >= b) || (a < c));               // 0 (FALSE)  
d = ((b != b) || (b > c)) && (c == a);   // 1 (TRUE) 
```

## Operator Bitwise

**Operator Bitwise**, seperti namanya digunakan untuk melakukan operasi pada dua operan dalam skala biner (bilangan basis 2). Sebelum mempelajari lebih lanjut cara kerja operasi bitwise, sebaiknya kamu harus paham terlebih dahulu mengenai bilangan dalam basis biner.

Terdapat 6 jenis operator bitwise, yakni **AND**, **OR**, **XOR**, **COMPELEMENT**, **SHIFT LEFT**, dan **SHIFT RIGHT**. Untuk lebih memahami perbedaan cara kerja operator bitwise, perhatikan tabel berikut.

| Operator                | Simbol | Keterangan                                                                                                                             |
| ----------------------- | :----: | -------------------------------------------------------------------------------------------------------------------------------------- |
| Bitwise AND             | &      | Mengevaluasi bit dari dua operan. Menghasilkan 1 apabila keduanya 1, jika tidak menghasilkan nilai 0.                                  |
| Bitwise OR              | \|     | Mengevaluasi bit dari dua operan. Menghasilkan 1 apabila salah satu nilainya 1, jika keduanya 0, maka menghasilkan nilai 0.            |
| Bitwise XOR             | ^      | Mengevaluasi bit dari dua operan. Menghasilkan 1 apabila bit pada kedua operan nilainya berbeda. Jika sama, maka menghasilkan nilai 0. |
| Bitwise COMPLEMENT      | ~      | Membalik semua nilai bit, dari 1 menjadi 0 dan 0 menjadi 1 (dalam panjang bit).                                                        |
| Bitwise SHIFT LEFT      | <<     | Menggeser bit ke kiri sebanyak n (operan kedua).                                                                                       |
| Bitwise SHIFT RIGHT     | >>     | Menggeser bit ke kanan sebanyak n (operan kedua).                                                                                      |

**Contoh penggunaan operator bitwise:**

Misal 12 dan 5. Representasi 12 dan 5 dalam basis biner adalah 12 = (1100) dan 5 = (0101). Maka, operasi bitwise adalah sebagai berikut.

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

    Misal kita hendak menggeser bit bilangan 13 ke kiri sebanyak 2, maka 13 << 2.

    ```
         13 = (001101)
    13 << 2 = (110100) 
    ```

    Bisa diperhatikan, bit paling kanan setelah digeser akan diisi oleh 0. Maka hasil dari 13 << 2 = 52.

+ **Bitwise SHIFT LEFT**

    Misal kita hendak menggeser bit bilangan 13 ke kanan sebanyak 2, maka 13 >> 2.

    ```
         13 = (001101)
    13 >> 2 = (000011)
    ```

    Bisa diperhatikan, bit paling kiri setelah digeser akan diisi oleh 0. Maka hasil dari 13 >> 2 = 3.

## Operator Gabungan

**Operator Gabungan** adalah operator yang terdiri dari gabungan dua operator. Tujuan dari operator gabungan adalah untuk mempersingkat penulisan kode. Berikut adalah operator gabungan dalam bahasa C.

| Operator | Contoh    | Ekuivalen Dengan        |
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

## Operator Lain

Selain operator-operator yang telah dijelaskan sebelumnya, terdapat beberapa operator lain yang terdapat pada bahasa C. Berikut penjelasannya.

### Operator `sizeof()`

Walaupun mempunyai bentuk seperti sebuah fungsi, namun dalam standardisasi bahasa C menganggap operator `sizeof()` sebagai operator. Kegunaan dari operator ini adalah untuk mengetahui besarnya alokasi memori sebuah operan (berupa variabel atau tipe data) dalam satuan byte.

Contoh:

```c
sizeof(int);
```

### Operator Address-of (`&`)

Operator ini mengembalikan alamat memori dari sebuah operan berupa variabel.

Contoh:

```c
int var;
printf("%d\n", &var);
```

### Operator Dereference (`*`)

Berbeda dari operator address-of (`&`), operator deference (`*`) mengembalikan nilai dari variabel pointer (akan dijelaskan pada modul pointer).

> Meskipun menggunakan simbol yang sama seperti operator perkalian, operator deference mempunyai fungsi yang benar-benar berbeda dari operator perkalian.

### Operator Kondisional (` ? : `)

Operator kondisial merupakan satu-satunya operator ternary (bekerja pada tiga operan) dalam bahasa C. Fungsi dari operator kondisional layaknya percabangan menggunakan `if - else` (akan dijelaskan pada modul percabangan).

### Operator Koma (`,`)

Tanda koma (`,`) sebagai operator dalam bahasa C merupakan binary operator yang akan mengevaluasi operan pertama, kemudian akan membuang hasilnya. Lalu mengevaluasi operan kedua dan akan mengembalikan nilainya.

```c
int number = (5, 23);   // number bernilai 23, bukan 5
```

Selain berfungsi sebagai operator, tanda koma (`,`) juga berfungsi sebagai separator (pemisah) antar statement. Misalkan saat deklarasi lebih dari satu variabel.

```c
int var1, var2, var3;   
// Menggunakan tanda koma untuk memisahkan deklarasi tiap variabel
```

> Tidak semua statement dapat dipisahkan oleh tanda koma.

### Operator Subscript (`[]`)

Penggunaan paling umum operator ini adalah untuk melakukan pengaksesan terhadap elemen suatu array (akan dibahas pada modul array).

_Operator lain yang belum ter-cover pada modul ini akan dibahas pada modul-modul selanjutnya._

[< Kembali ke Daftar Isi](#daftar-isi)
