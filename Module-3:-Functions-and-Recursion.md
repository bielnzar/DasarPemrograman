## Table of Contents
- [Functions](#function)
   + [Defining A Function](#defining-a-function)
   + [Function Prototypes](#function-prototypes)
   + [Function Parameters](#function-parameters)
   + [Function Return Values](#function-return-values)
- [Recursive Functions](#recursive-functions)
   + [Recursive Case and Base Case](#recursive-case-and-base-case)

***

# Functions

## Introduction to Functions
A **function** is a set of statements that execute a specific task, with or without input, to return a correct output.

In general, functions are categorized into two, standard library functions and user-defined functions. **Standard library functions** are built-in functions from standard libraries. For instance, `printf()` and `scanf()` are defined in the library stdio.h. **User-defined functions** are functions that are made custom by the user to fulfill certain needs in the program.

## The Objectives of Functions
Functions are made so that programs can be more modular. They are usually used when we want to execute a group of commands for several times, sometimes with different input values, **without having to write the code pieces repeatedly**. Aside from that, functions are also made to enable easier debugging.

## Defining A Function
Before a function can be executed through a function call, we need to define it first. **Function definition** is needed to explain what the function will do if it is called for execution.

Below is the syntax for function definition in C:

```
<return_type> <function_name>(<parameter1>, <parameter2>, ...)
{
    statement;
    statement;
    ...
    ...
    ...
}
```

Below is an example of a function that prints the string **"I am a function."**:

```c
void print()
{
    printf("I am a function\n");
}
 
int main()
{
    print();
    return 0;
}
```

## Function Prototypes
Aside from defining a function since the start like we did in the previous example, we can also begin by making a function prototype. A **function prototype** declares a function without its definition. This declaration only contains the return type, name, and parameters of the function.

Below is the syntax for function prototypes:

```
// Declaration
<return_type> <function_name>(<parameter1>, <parameter2>, ...);
```

Code example of using a function prototype:

```c
void print();        // Function prototype
 
int main()
{
    print();
    return 0;
}
 
void print()         // Function definition
{
    printf("I am a function\n");
}
```

## Function Parameters
**Parameters** in a function can be seen as input to that function. There can be as many parameters passed to a function as needed. Function parameters are defined in a similar way to a variable. Each parameter is separated by the comma (,) operator.

```
<data_type_1> <parameter_1> , <data_type_2> <parameter_2>, ...
```

Example:
```c
void print(char str[])
{
    printf("%s\n", str);
}
 
void sum(int a, int b)
{
    int total = a + b;
    printf("%d\n", total);
}
```

## Function Calls
To call a function, function name is written, followed by a pair of brackets `()` containing parameters passed to that function. If the function requires parameters passed to it, then we take the right values/variables/objects to be passed as arguments separated by the operator `,`. **Arguments passed need to have the same sequence and data types as the function parameters.**

Example of a function call:

```c
int main()
{
    print();
    sum(2,5);
    print("Hello, world");
}
```

## Function Return Values
If we want a function to return a value or simply outputs something, add the keyword `return` to the function and define the return type of this function (same data type as the return value). Functions that have a return type other than *`void`* must return a value. 

When the statement `return` is found on a function, then the program will halt the function execution on the point of that return statement, then returns to the part of the code where the function was called.

Suppose we want to obtain the result of a simple addition of **a** and **b** through the function `sum()`.

```c
#include <stdio.h>
 
int sum(int a, int b);
 
int main()
{
    int x = 2, y = 3, result;
    result = sum(x, y);
    printf("%d\n", result);
    return 0;
}
 
int sum(int a, int b)
{
    int result = a;
    result += b;
    return result;
}
```

# Recursive Functions

## Introduction to Recursion
**Recursion** refers to a procedure that is repeated and is defined in terms of itself.

![image](https://miro.medium.com/max/719/1*y3-7Dh1DIsm5Ut9OZjmXTg.jpeg)

The above figure is a representation of recursion. In programming, the term recursion is used to describe a function that is recursive.

**A recursive function** is a function that may call upon itself while executing. See the below code example:

```c
#include <stdio.h>
 
void recursion(int n)
{
    printf("%d\n", n);
    recursion(n+1);       // calls itself
}
 
int main()
{
    recursion(1);
    return 0;
}
```

The function `recursion()` is a recursive function because inside it there exists a call to itself.

## Recursive Case and Base Case
The previous code example will keep on printing the value of **n** becaue the function doesn't know when to stop calling itself. Because of that, we need to define a **base case** in recursive functions.

A **base case** is a terminating condition that we provide the recursive function with so that it is able to stop calling itself.

Meanwhile, a **recursive case** is a condition where a recursive function has to call itself, or in other words where a recursive function has not reached its base case.

Let's take an example of exponentiating a number using a recursive function. Firstly, let's define the power of an integer **a** to an integer **m** as **`power(a, m)`**, therefore it can be written as below:

<a href="https://www.codecogs.com/eqnedit.php?latex=power(a,&space;m)=a\times&space;a\times&space;a\times&space;\cdots&space;(m-kali)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?power(a,&space;m)=a\times&space;a\times&space;a\times&space;\cdots&space;(m-kali)" title="power(a, m)=a\times a\times a\times \cdots (m-times)" /></a>

Or, recursively:
<a href="https://www.codecogs.com/eqnedit.php?latex=power(a,&space;m)=a\times&space;power(a,m-1)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?power(a,&space;m)=a\times&space;power(a,m-1)" title="power(a, m)=a\times power(a,m-1)" /></a>

With the *base case*:
<a href="https://www.codecogs.com/eqnedit.php?latex=power(a,&space;0)=&space;1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?power(a,&space;0)=&space;1" title="power(a, 0)= 1" /></a>

The *base case* of the function `power(a, m)` is when `power(a, 0)` is executed, which returns 1. After the *base case* is reached, there's no need for further calls.

```c
#include <stdio.h>
 
int power(int a, int m)
{
    if (m == 0) return 1;       // base case
    return (a * power(a, m-1)); // recursive case
}
 
int main()
{
    printf("%d\n", power(2,3));
    return 0;
}
```

# Exercise

Given a number, determine whether that number can reach 42 or not with the rules below:
1. If the number is even, then subtract half of that number from it.
2. If the number is divisible by 3 or 4, then subtract the result of the last 2 digits' multiplication from it.
3. If the number is divisible by 5, then subtract 42 from it.

**Use recursion.**

**Input Format**

The first line contains **T** which represents the amount of test cases. The next T-lines are integers to be determined according to the rules in the problem description.

**Output Format**

If T is able to reach 42 through any of those rules, print "Yes".
Otherwise, print "No".

**Sample Input**
```
1
250
```

**Sample Output**
```
Yes
```

**Explanation**

T = 250
+ 250 is divisible by 5, therefore `250 - 42 = 208`.
+ 208 is an even number, therefore `208 - 104 = 104`.
+ 104 is an even number, therefore `104 - 52 = 52`.
+ 52 is divisible by 4, therefore `52 - (5*2) = 42`.
Because we have reached 42, then print the output "Yes".

**Constraints**

+ 1 ≤ T ≤ 5000
+ 1 ≤ N ≤ 1000000000