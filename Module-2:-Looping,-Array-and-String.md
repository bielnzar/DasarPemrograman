## Table of Contents
- [Looping](#looping)
    + [While Loop](#while-loop)
    + [Do-While Loop](#do-while-loop)
    + [For Loop](#for-loop)
    + [Nested Loop](#nested-loop)
- [Break and Continue](break-and-continue)
- [Infinite Loop](#infinite-loop)
- [Array](#array)
    + [Array Introduction, Declaration, Initialization](#introduction-to-array)
    + [Accessing Array Elements](#accessing-array-elements)
    + [Array Dimensions](#array-dimensions)
- [String](#string)
    + [String Introduction and Representation](#introduction-to-string)
    + [String Functions](#string-functions)
- [Exercises](#exercises)

# Looping

Looping enables us to execute a part of a code for multiple times, until a certain condition is reached. There are 3 methods of looping in C: `while`, `do - while`, and `for`.

## While Loop

The `while` loop is the simplest loop method. The syntax is as follows.

```c
//initial value of iterator (ex: i = 0)
while (<expression/condition>) {
    // Code to execute multiple times
    .
    .
    .
    // increment/decrement iterator (i++)
}
```
The `while` statement works in a similar way to `if`. In **if** statement, the part of code will be executed for **only once**, if the expression/condition is equivalent to **TRUE**, meanwhile in **while** statement, it will be executed for as long as the expression/condition is not equivalent to **FALSE**.

Example:
```c
#include <stdio.h>

int main()
{
    int i = 0;
    while (i < 10)
    {
        printf("Hello World! loop-%d \n",i);
        i++;
    }
    return 0;
}
```

On the example above:
- Initially, the variable **`i`** is equal to 0.
- The next sequence is `while`, and i is still less than 10 at this point (**TRUE**), thus the code inside `while` will be executed.
- After printing "hello world", the variable **`i`** will be incremented, and the program will go back to the `while` statement to check whether **`i`** is still less than 10 at this point.
- **`i`** is not less than 10 (because it has been incremented), so the code inside `while` will be executed again until **`i`** is equal to 10 (which means the condition in the `while` statement evaluates to **FALSE**

## Do-While Loop

The syntax for the `do - while` loop is as follows.
```c
do {
    // Code to be executed
    .
    .
    // increment/decrement
} while (<expression/condition>)
```

The `do - while` loop is similar to `while`, but in `do - while`, the code inside it is executed exactly one time before evaluating the expression/condition.

Example:
```c
#include <stdio.h>
int main()
{
    int num = 0;
    do
    {
        printf("Num is now %d\n",num);
        printf("Enter a positive integer (-1 to terminate the program): ");
        scanf("%d", &num);
    } while (num != -1);
    return 0;
}
```

## For Loop

The `for` loop is the most complicated among the others, the syntax is as follows.

```c
for (init_statement; expression/condition; end_statement) {
    //  Code to be executed
    .
    .
}
```

How it works:
- `init_statement` is used to initialize an iterator variable that is going to be used in the looping process. This part is only executed once in the beginning of the loop.
- After that, `expression/condition` will be evaluated. If it evaluates to **TRUE**, then the loop will execute the code inside. Otherwise, the loop is terminated.
- After the code finishes executing, the program will execute `end_statement`. Usually, this part is used to increment/decrement the iterator.
- The program will **evaluate the expression/condition again**, and continue with the steps above.

Example:
```c
#include <stdio.h>
int main()
{
    int i;
    //    init; condition; increment
    for (i = 0; i < 10  ; i++) {
        printf("Hello World!\n");
    }
}
```

On the example above:
1. Initially, **`i`** is equal to 0.
2. For statement will check whether **`i`** is less than 10.
3. If **TRUE**, then the code inside the `for` block will be executed.
4. After the code inside the block finishes executing, then **`i`** will be incremented and evaluated again.
5. If **`i`** is less than 0, then the code inside the block will be executed, otherwise the loop is terminated.

## Nested Loop

Looping can also be nested (loops inside loops) as needed. The example below is a nested `for` loop.

```c
int i, j;
for (i = 1; i <= 10; ++i) {
    // Outer level statements

    for (j = 1; j <= 10; j++) {
        // Inner level statements

        // Loop inside a conditional statement
        if (i == 10) {
            // Do something
        }
    }
    // Outer level statements
}
```

# Break and Continue
The keywords `break` and `continue` are used to control the flow in a loop.

## Break
`break` is used to **force terminate** a loop. If a `break` commmand exists in a loop, then that loop will be force terminated at the point where the `break` command is at.

Example:
```c
#include <stdio.h>

int main()
{
	int i;
	for (i = 1; i <= 6; i++) {
		printf("%d\n", i);
		//   If i is equal to 4, then terminate the loop
		if (i == 4) {
			break;
		}
	}
	return 0;
}
```

## Continue

In contrast with the `break` statement, the `continue` statement is used to **continue a loop**. In a looping, if a `continue` statement is found, then the commands inside `continue` will be **ignored** and the program will go on to **evaluate the loop expression/condition**. Meanwhile, in a `for` loop, the program will go on to execute the end_statement part before evaluating the loop expression/condition.

Example:
```c
#include <stdio.h>

int main()
{
	int i;
    for (i = 1; i <= 6; i++) {
        if (i == 4) {    // If i=4, ignore printf command
            continue;
        }
        printf("%d\n",i);
    }
    return 0;
}
```

# Infinite Loop

Infinite loop is the case when a loop isn't terminating. This happens when a loop isn't able to reach a condition that terminates it.

Example:
```c
#include <stdio.h>

int main()
{
    int i;
    for (i = 1; i <= 100; i--) {
        // Loop doesn't stop
    }
}
```

# Array

## Introduction to Array

Array is a data structure that contains elements of the same data types sequentially with a fixed capacity and is addressed with one *identifier*.

## Array Declaration

Array is similar with variable, it needs to be declared first before it can be used. Array declaration needs its size declared as well.

```
data_type array_identifier[size];
```

## Array Initialization

We can initialize array elements after the array is declared. The syntax is as follows.

```
data_type array_identifier[size] = {elem1, elem2, elem3, ....}
```

## Accessing Array Elements

As been said before, array is stored sequentially in a memory block. Accessing array elements can be done by writing the array identifier combined with a subscript operator `[]` containing the index of the element to be accessed.

![akses_array](https://github.com/AlproITS/DP_modul-2/blob/master/img/Array_access.png)

Array uses zero-based indexing, which means the first element in an array is addressed as the 0-th index (not the 1-st), and the last element is addressed as the (N-1)-th index (where N is the length of the array). The elements inside an array can be treated like a variable, we can assign a value to it, do arithmetic operations, etc.

Example:
```c
int main () 
{
  int a[10]; // Array declaration
  
  int b[5] = {1, 2, 3, 4, 5}; // Array initialization
  
  a[0] = 50;
  a[1] = 20;
  
  printf("%d %d\n", a[0], a[1]);
  
  return 0;
}
```

Why do we need arrays? Suppose we need to input 1000 data, we don't need to declare 1000 different variables (a1 to a1000). Instead, we can declare 1 array identifier with a capacity of 1000.

Example of program without array:
```c
int main () {

  int a, b, c, d, e; // Declaration of 5 integer variables
  
  scanf("%d %d %d %d %d", &a, &b, &c, &d, &e);
  
  printf("First %d\n, a);
  printf("Second %d\n, b);
  printf("Third %d\n, c);
  printf("Fourth %d\n, d);
  printf("Fifth %d\n, e);
  return 0;

}
```

Example of program with array:
```c
int main () 
{
	int a[5], i; 
	for(i = 0; i < 5; i++) {
		scanf("%d", &a[i]); //Input array
	}

	for(i = 0; i < 5; i++) {
		prinf("Number-%d is %d\n", i+1, a[i]; // Output array
	}

	return 0;

}
```
## Array Dimension

### One Dimensional Array

An array is one dimensional if every element stores only one data/object. The examples that have been provided so far are of one dimensional array.

One dimensional array:
```c
int main()
{
	int arr[5];
	arr[0] = 4;
	arr[1] = 2;
	arr[2] = 3;
	return 0;
}
```

If illustrated, the above array will look like the picture below.

![array-satu-dimens](https://github.com/AlproITS/DP_modul-2/blob/master/img/1D_Array.png)

### Multidimensional Array

An array is multidimensional when every element contains another element. A multidimensional array has two or more indexes to access its elements. 

Declaring a multidimensional array is different from a one dimensional array. We will need N subscript operators `[]` to make an array with N-dimensions.

Multidimensional array:
```c
int main () 
{
	int matrix[5][6];
	matrix[2][3] = 100;
	matrix[1][4] = 200;
	return 0;
}
```

If illustrated, the form of a two dimensional array is similar to a matrix, with a row and a column.

![array-dua-dimensi](https://github.com/AlproITS/DP_modul-2/blob/master/img/2D_Array.png)

# String

## Introduction to String

In general, a string is a collection of one or more characters. In C, specifically, a string is defined as a collection of characters ended with a null character (`'\0'`).

Say we have a string `"Dasar"`, then in C it is represented as a collection of characters `'D'`, `'a'`, `'s'`, `'a'`, `'r'`, and `'\0'`.

## String Representation

In C, a string is represented as an array of type `char`.

Example:
```c
#include <stdio.h>

int main () 
{  
	char str[] = "Halo"; 
	return 0;
}
```

The example above will declare a string called **str** with a capacity of 5 characters, where `str[0] = 'H'`, `str[1] = 'a'`, `str[2] = 'l'`, `str[3] = 'o'`, and `str[4] = '\0'`.
Notice how str[4] is equal to the character '\0' (null character), even though in the string literal **str** there's no such character. In C, the null character is used to mark **the end of a string**.

Example:
```c
#include <stdio.h>

int main () {
  char array[10];
  
  return 0;
}
```

The example above will declare a string called array that can contain a maximum of 10 characters, indexed 0 to 9, including the null character at the end.

To receive a string input from user, we can use the `scanf` or `gets` command. The command `scanf` will read the string input from user and stop when it encounters a *whitespace* or an interruption from user. Meanwhile, `gets` will read a whole line of characters until it encounters a *newline* or an interruption from user.

Example of `scanf`:
```c
#include <stdio.h>

int main () {
  
	char array[10];
	while(true)
	{
		scanf("%s", arr);
		printf("-- %s\n", arr);
	}
	return 0;

}
```

Example of `gets`:
```c
#include <stdio.h>

int main () {
  
	char arr[100];
	while(true)
	{
		gets(arr);
		
		printf("-- %s\n", arr);
	}
        return 0;

}
```
A string that is read using `scanf` or `gets` will automatically has a null character at its end.

##  String Functions

In C, there is a library that's made to accommodate users in string processing. That library is stored in the header file `<string.h>`. Thus, to access that library we need to add a preprocessor:

```c
#include <string.h>
```

Below are functions that exist in string.h, grouped according to their functionality in string processing (taken from www.cplusplus.com):
- **Copying**
  + `memcpy` (Copy block of memory)
  + `memmove` (Move block of memory)
  + `strcpy` (Copy string)
  + `strncpy` (Copy characters from string)
- **Concatenation**
  + `strcat` (Concatenate strings)
  + `strncat` (Append character from string)
- **Comparison**
  + `memcmp` (Compare two blocks of memory)
  + `strcmp` (Compare two strings)
  + `strcoll` (Compare two strings using locale)
  + `strncmp` (Compare characters of two strings)
  + `strxfrm` (Transform string using locale)
- **Searching**
  + `memchr` (Locate character in block of memory)
  + `strchr` (Locate first occurrence of character in string)
  + `strcspn` (Get span until character in string)
  + `strpbrk` (Locate characters in string)
  + `strrchr` (Locate last occurrence of character in string)
  + `strspn` (Get span of character set in string)
  + `strstr` (Locate substring)
  + `strtok` (Split string into tokens)
- **Other**
  + `memset` (Fill block of memory)
  + `strerror` (Get pointer to error message string)
  + `strlen` (Get string length)

Here are some functions and their explanations.

### `strcpy` 
```c
char * strcpy ( char * destination, const char * source );
```
The `strcpy` function is used to **copy** a string to another string. 

Usage example:
```c
#include <stdio.h>
#include <string.h>

int main () {
  
	char a[] = "Halo";
	char b[10];
	
	// Copy string a to string b
	strcpy(b, a);
	
	printf("%s\n", b);
	
	return 0;

}
```

### `strcat`
```c
char * strcat ( char * destination, const char * source );
```
The `strcat` function is used to concatenate a string to the **end** of another string. 

Usage example:
```c
#include <stdio.h>
#include <string.h>

int main () {
  
	char a[] = "Halo";
	char b[] = " Kawan";
	char c[20];
	
	// Copy string a ke string b
	strcpy(c, a);
	
	// Tempelkan string b ke akhir string c
	strcat(c, b);
	
	printf("%s\n", c);
	
	return 0;

}
```

### `strcmp`
```c
int strcmp ( const char * str1, const char * str2 );
```
The `strcmp` function is used to **compare** a string with another string. The return value of this function is either a negative, 0, or a positive value. If this function returns a **negative** value, then *str1* has a lower lexicographical order than *str2*. If it returns a **positive** value, *str1* has a bigger lexicographic order. If it returns **0**, then *str1* is the same as *str2*

Usage example:
```c
#include <stdio.h>
#include <string.h>

int main () {
  
    char a[] = "Halo";
	char b[] = "Hai";
	char c[] = "Halo;
	
	if(strcmp(a, b) == 0) printf("String a is the same as b\n");
	else printf("String a is not the same as b\n");
	
	if(strcmp(a, c) == 0) printf("String a is the same as c\n");
	else printf("String a is not the same as c\n");
	
	return 0;

}
```

### `strlen`
```c
size_t strlen ( const char * str );
```
The `strlen` function is used to get the **length** of a string.

```c
#include <stdio.h>
#include <string.h>

int main () {
  
	char a[] = "Halo";
	
	printf("The length of string a is %d\n", strlen(a));
	
	return 0;

}
```

# Exercises

### Exercise 1

Create a program that prints the word `Odd` for every input that is an odd number, and `Even` for every input that is an even number.

**Sample Input**

```
1
```

**Sample Output**

```
Odd
```

### Exercise 2

Create a program that prints an asterisk (`*`) for even numbers and its real value for odd numbers, for n numbers from 1 to n.

**Sample Input**

```
6
```

**Sample Output**

```
1 * 3 * 5 *
```
    
### Exercise 3

Create a program that prints an asterisk (`*`) for prime numbers and its real value for non-prime numbers for n numbers from 2 to n.

**Sample Input**

```
10
```

**Sample Output**

```
* * 4 * 6 * 8 9 10
```

### Exercise 4

Create a program that prints N numbers of input in reverse. The first input line consists of N, which is the amount of input. In the next line there are N-inputs separated by a space.

**Sample Input**

```
5
1 4 3 2 9
```

**Sample Output**

```
9
2
3
4
1
```

### Exercise 5

Create a program that counts how many vowels there are in a string S. The length of string S is not more than 100 characters and it can consists of lowercase, uppercase, or space characters.

**Sample Input**

```
Basic Programming is Cool
```

**Sample Output**

```
A/a : 2
I/i : 3
U/u : 0
E/e : 0
O/o : 3
```

### Exercise 6

Given a variable name in the format of **snake_case**. Create a program to change that variable's name to the format of **camelCase**. The variable's name can only consists of lowercase letters, uppercase letters, and the underscore (`_`).

**Sample Input 1**

```
player_score
```

**Sample Output 1**

```
playerScore
```

**Sample Input 2**

```
VariabEl_OnE
```

**Sample Output 2**

```
variabelOne
```
