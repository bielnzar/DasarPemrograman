## Table of Contents

- [IDE (Integrated Development Environment)](#ide-intregated-development-environment)

- [Introduction to the C Language](#pengenalan-bahasa-c)

    + [Statement](#statement)
    + [Program "Hello, world."](#program-hello-world)
    + [Program Structure](#struktur-program)
    + [Comments](#komentar)

- [Keywords and Identifiers](#keyword-dan-identifier)

    + [Keywords](#keyword)
    + [Identifiers](#identifier)

- [Variables](#variabel)

    + [Introduction to Variables](#pengenalan-variabel)
    + [Variable Declaration and Definition](#deklarasi-dan-definisi-variabel)
    + [Assigning a Value](#pengisian-nilai-variabel)
    + [Initializing a Variable](#inisialisasi-variabel)

- [Constants and Literals](#konstanta-dan-literal)

    + [Constants and Literals](#konstanta-dan-literal-1)
    + [Defining a Constant](#mendefinisikan-konstanta)

- [Basic Data Types](#tipe-data-dasar)

    + [Integer Type](#tipe-bilangan-bulat-integer)
    + [Real Number (floating point) Type](#tipe-bilangan-real-floating)
    + [Character Type](#tipe-karakter)

- [Basic Input and Output](#input-dan-output-dasar)

    + [Basic Output](#output-dasar)
    + [Basic Input](#input-dasar)

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

**Komentar** (_comment_) adalah bagian dari program yang tidak akan dieksekusi. Komentar sangat berguna untuk mendeskripsikan program yang dibuat, misalnya saja untuk menjelaskan bagian dari kode agar mudah dipahami oleh programmer lainnya. Terdapat dua jenis komentar dalam bahasa C.

### Komentar Single-Line

Seperti namanya, komentar single-line hanya bekerja pada satu baris. Komentar single-line diawali dengan simbol `//` . Semua karakter (pada satu baris) dibelakang simbol `//` akan diabaikan.

```c
// Ini adalah komentar single-line  
  
// Fungsi untuk mencetak ke layar  
printf("HALO\n");  

```

### Komentar Multi-Line

Sedangkan komentar multi-line dapat bekerja pada lebih dari satu baris. Pasangan simbol `/*` dan `*/` digunakan untuk membuat komentar multi-line. Semua karakter yang berada di antara dua simbol tersebut akan diabaikan.

```c
/* 
Ini adalah komentar multi-line 
Semua yang berada di sini akan 
diabaikan 
*/  
```
[< Kembali ke Daftar Isi](#daftar-isi)