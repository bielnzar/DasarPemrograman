## Table of Contents

- [Control Flow](#control-flow)
- [Branching](#branching)
    + [If](#if)
    + [If-Else](#percabangan-if-else)
    + [If-Else if](#percabangan-if-elseif)
    + [Switch-Case](#percabangan-switch-case)
    + [Operator Kondisional ( ? : )](#operator-kondisional--)

# Control Flow
Control Flow is how we manage the path of statements, instructions, and function calls of a program. Without control flow, our program only moves from top to bottom (**sequential**). There are 2 types of control flow in C language: branching (**selection**) and repetition.

# Branching
Branching allows us to specify which part of code to execute based on a condition. There are 4 ways we can implement branching in the C language, which are by using `if`,` if-else`, `if-else if`, and `switch-case` statements.

## If Statement

The syntax used in branching using `if` is as follows.

if (<Expressions / Conditions >) {

// Code to be executed if the condition is true

}

The way the `if` branch works is it checks and evaluates a condition to determine whether the next instruction in the bracket will be executed or not by the program.
- If the condition is  **TRUE (1)**, the code inside bracket will  be executed.
- Otherwise if the condition is **FALSE (0)**, the code inside bracket will not be executed.

Example:

For example, on a car dashboard there is a fuel indicator that will light up if the remaining fuel is less than a certain level (for example less than 10 litres). To evaluate the level of fuel, we ask: "Is the fuel less than 10 litres?".

In this case there is a condition
- **If the fuel is less** than 10 liters, then turn on the indicator light.

```c
#include <stdio.h>
int main()
{
    int gasoline = 0;
    gasoline = 3;
    
    if (gasoline < 10) // If fuel is less than 10 liters
    {
         // Put here what needs to be done when the conditions are met
         printf ("The indicator light is on! \n");
    }
}
```

Output
```
The indicator light is on!
```

## If-Else Statement

The syntax used in branching using `if-else` is as follows.

if (<Expression / Condition>) {

    // Code to be executed if the condition is true

} else {

    // Code to be executed if the condition is false

}

The way the `if-else` statement works is to check the conditions in the `if`.
- **If the condition is TRUE (1)**, the program  will execute the code inside the **`if`** bracket.
- Conversely, **if the condition is  FALSE (0)**, the code below **`else`** will be executed.

Example

For example, we want to find out whether someone is absent from class or not. **If one is absent, their attendance will be crossed out (worth X)**, while **if present, then their attendance will be ticked (worth V) **.

So from this case, two alternative conditions are obtained.
- **If he is present, then V appears**
- **If he is not present, X  will appear**

```c
#include <stdio.h>
#define COME 1

int main ()
{
    int present = COME;
    if (present) // If the person is present
    {
        printf("V\n");
    } else {
        printf("X\n");
    }
}
```

Output
```
V
```

## If-Else if Statement

The syntax used in branching using `if-else if` statement is as follows.

```c
if (<Expression / Condition>) {

    // Code to be executed if the condition is true

} else if (<Expression / Condition>) {

    // Code to be executed if the condition is false

}
// May add else {} if necessary
```

The way the `if-else if` branch works is to check the conditions in the `if`.
- If the condition evaluates to **TRUE (1)**, the program  will execute the code inside the **`if`** bracket.
- If the first condition not fulfilled, then it will check the condition in **`else if`**, if it evaluates to **TRUE (1)**, then it will execute the command in that bracket, otherwise it will run the next sequence.
- If we provide an **`else`** statement at the end, then when all conditions in `if` and `else if`s are not fulfilled or evaluate to **FALSE (0)**, the program will automatically execute the command inside the `else` statement.

## Percabangan Switch-Case

Apart from using the `if` statement to choose between many alternatives, there is also a `switch` statement which has the same function, which is to choose between many alternatives based on a condition. The condition in a `switch` statement contains an expression of a single variable of type int or char whose values will be checked in each case block.

Syntax for `Switch-Case`:

```c
switch (expression) {
    constant-expression case:
        statement;
        break;

    constant-expression case:
        statement;
        break;
  
    /* You can have as many cases as possible */

    /* Default is compulsory to be added to the end of a switch-case statement.
       The below block of code will be executed when none of the cases above are fulfilled. */

    default:
        statement;
}
```

For each case block, the statement  `break` must be added to the end, because if not then it will continue to run the case block underneath it until it meets another break or reaches the end of the switch block.

Example

```c
#include <stdio.h>

int main()
{
    char plateNumber;
    printf("Enter the first letters of your license plate: ");
    scanf("%c", &plateNumber);
    
    switch (plateNumber)
    {
        case 'L':
            printf("Surabaya");
            break;

        case 'B':
            printf("Jakarta");
            break;

        case 'D':
            printf("Bandung");
            break;

        case 'N':
            printf("Malang / Lumajang");
            break;

        default:
            printf("Unknown plate number character");
    }
    return 0;
}
```

On the example above, the  expression  used is **plateNumber**, where the **cases** are the license plate letters: L, B, D, N, and so on.

## Operator Kondisional (` ? : `)

The syntax for conditional operator is as follows:

```
(expression/condition) ? (expression if TRUE) : (expression if FALSE);
```

The conditional operator is the only ternary operator in C. The conditional operator acts like the `if-else` statement. The expression or condition to be evaluated is written before the question mark (`?`). If it evaluated to **TRUE**, then the program will execute the expression to the left of the colon (`:`). In opposite, if it evaluates to **FALSE**, then the program will execute the expression to the right of the colon.

Example:

```c
#include <stdio.h>

int main()
{
    int mark;
    
    scanf("%d", &mark);
    printf(mark >= 75 ? "Lulus\n" : "Tidak Lulus\n");
    return 0;
}
```

The above program is equivalent to:

```c
#include <stdio.h>

int main()
{
    int mark;
    
    scanf("%d", &mark);
    if (mark >= 75) {
        printf("Lulus\n");
    } else {
        printf("Tidak Lulus\n");
    }
    return 0;
}
```