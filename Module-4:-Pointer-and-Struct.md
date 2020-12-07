## Table of Contents
- [Pointer](#pointer)
   + [Memory Address](#memory-address)
   + [Introduction to Pointer](#introduction-to-pointer)
   + [Double Pointer](#double-pointer)
   + [Pointer and Array](#pointer-and-array)
   + [Pointer and Fungsi](#pointer-and-fungsi)
- [Struct](#struct)
   + [Introduction to Struct](#introduction-to-struct)
   + [Struct Declaration](#struct-declaration)
   + [Struct Variables](#struct-variables)
   + [Accessing Struct Members](#accessing-struct-members)
   + [Array of Struct](#array-of-struct)
- [Exercises](#exercises)

***

# Pointer

## Memory Address

### Address-Of Operator (&)

Every variable, function, struct, or other object created in the program has its own location in memory. The allocation of each variable is stored in a specific memory address.

Example:\
There is a variable named var. To find the memory address of a variable, use the address-of (&) operator in front of the variable name.

Setiap variabel, fungsi, struct, ataupun objek lain yang dibuat dalam program mempunyai lokasi masing-masing pada memori. Alokasi setiap variabel disimpan dalam alamat memori tertentu. 

```C
int var = 5;
printf("%d\n", var);
printf("%p\n", &var);
```

**Output**:
```
5
0x7fffdeb3ed84
```

The output may differ for each execution.\
0x7fffdeb3ed84 is the memory address of the `var` variable.

***

## Introduction to Pointer 

Pointers are fun and easy to learn. A pointer is a special variable that holds a memory address instead of a value like regular variables.

### Pointer Variable Declaration

A pointer variable declaration uses the `*` operator between the data type and the variable name.

```C
int *ptr;
```
or
```C
int* ptr;
```
Both methods are valid.

### Pointer Variable Initialization

The `ptr` variable above is a pointer variable of type int. The pointer variable holds a memory address. The initialization of the pointer variable must be a memory address, it can be from other variables or dynamic allocation.

```C
int var = 55;
int *ptr = &var; // Inisialization uses the address of var
```

Improper initialization will result in an error or undefined behavior.

```C
// ERROR
int *ptr  = 5;
// UNDEFINED BEHAVIOUR
int *ptr2 = 0x7fffdeb3ed84;
```

### Pointer Variable Assignment

Pointer variable assignment is not the same as pointer initialization.

```C
int var, *ptr;
var = 55;
ptr = &var; // assignment  to a pointer variable using the address of var
```

When assigning a pointer variable, we don’t need to use the * symbol in front of the variable name. It's different from when the declaration where we need to tell the compiler that the variable is a pointer variable.

### Dereference Operator (*)

The dereference operator uses the same symbol as the multiplication operator symbol, which is * (asterisk symbol). However, their functions are very different. The dereference operator is used to access the value pointed from a pointer variable.

To access the value of a pointer variable, use the dereference operator in front of the pointer variable’s name.

```C
int var  = 55;
int *ptr = &var;

printf("%d\n", *ptr);
*ptr = 20;

printf("%d\n", *ptr);
printf("%d\n", var);
```

**Output**
```C
55
20
20
```

What is the output of the below program?
```C
#include <stdio.h>

int main(void)
{
    int x, y, z;
    int *ptr1, *ptr2;
    x = 5;
    y = 6;

    ptr1 = &x;
    ptr2 = &y;

    z = *ptr1 + *ptr2;
    printf("%d\n", z);
    
    return 0;
}
```

## Double Pointer

A pointer variable can also point to other pointer variables. This is known as a **double pointer** (pointer to pointer). To declare a double pointer variable, use two symbols *. The most common use of double pointer variables is to dynamically create two-dimensional arrays.

```c
int **dbPtr;
```
The variable `dbPtr` above stores the memory addresses of other pointer variables.

```c
#include <stdio.h>

int main(void)
{
    int var = 23;
    int *ptr = &var;
    int **dbPtr = &ptr;

    printf("%d\n", **dbPtr);
    
    return 0;
}
```

## Pointer and Array

We already know that an array is a collection of data arranged sequentially. Because they are arranged sequentially, the memory addresses of each element of the array are also arranged sequentially.

![memory](https://github.com/AlproITS/DasarPemrograman/blob/master/img/memory.PNG)

How to find out the memory address of an array?

```c
#include <stdio.h>

int main()
{
    int arr[5] = {1, 2, 3, 4, 5};
    int i;
    for (i = 0; i < 5; ++i) {
        printf("&arr[%d] => %p\n", i, &arr[i]);
    }
    printf("Address of arr => %p\n", arr);
    return 0;
}
```

**Output**
```
&arr[0] => 0x7fffe85f0520
&arr[1] => 0x7fffe85f0524
&arr[2] => 0x7fffe85f0528
&arr[3] => 0x7fffe85f052c
&arr[4] => 0x7fffe85f0530
Address of arr => 0x7fffe85f0520
```

It can be seen that the address of `&arr[0]` is the same as the address of `arr`. It is also known that the array name points to the first element of the array. Because `&arr[0]` = `arr`, it can be concluded that `arr[0]` = `*arr`, or the value of the first element can be accessed by `*arr` or `*(arr + 0)`.

arr[0] = *(arr + 0)\
arr[1] = *(arr + 1)\
arr[2] = *(arr + 2)\
.\
.\
etc.

**Conclusion**: The array name refers to the memory address of the first element in the array. Based on that, we can do access array elements by calling the array name + the index.

```c
#include <stdio.h>

int main()
{
    int arr[5] = {1, 2, 3, 4, 5}, i;
    int *ptr = arr;

    for (i = 0; i < 5; ++i) {
        printf("%d ", *(ptr+i));
    }
    return 0;
}
```

**Output**
```
1 2 3 4 5
```

## Pointer dan Functio

In the previous module, we have learned that function can accept arguments as input. But we only have been passing variables to a function **by value**. There is another way to pass variables to functions.

<img src="https://blog.penjee.com/wp-content/uploads/2015/02/pass-by-reference-vs-pass-by-value-animation.gif">

### Pass by Value

**_Pass by Value_** means that when we pass an argument to a function, the value of the argument will be copied to the variable that is in the function parameter. Because only its value is accepted by the function, changes which occur in the function parameter variable will not affect the original variable.

Example:
```c
#include <stdio.h>

void change(int a, int b)
{
    a = a + 5;
    b = b + 5;
}

int main()
{
    int x = 10, y = 6;
    change(x, y);
    printf("%d %d\n", x, y);

    return 0;
}
```

**The values ​​of the x and y variables do not change because the passing method used is Pass by Value.**.

### Pass by Address/Reference

Unlike the previous one, as the name implies, the Pass by Address method means that the argument passed to the function parameter is the variable memory address. **All changes that occur in these variables will directly affect the original variables.** This happens because the argument is a memory address.

```c
#include <stdio.h>

void change(int *a, int *b)
{
    *a = *a + 5;
    *b = *b + 5;
}

int main()
{
    int x = 10, y = 6;
    change(&x, &y);
    printf("%d %d\n", x, y);

    return 0;
}
```

Since the parameter accepts a memory address, the parameter variable must be a pointer.

Passing arrays as function parameters can also be done with pointers. Any changes to the array will also affect the original array.

```c
#include <stdio.h>

void printArr(int *arr)
{
    // ...
    // ...
}

int main()
{
    int num[5] = {1, 2, 3, 4, 5}, i;
    printArr(num);
    // ...
    // ...
    return 0;
}
```

# Struct

## Introduction to Struct

In C language, struct is a derived data type or it can be called as **user defined data type** which can collect several variables under one name. Unlike arrays which can only store elements of the same data type, **structs can collect elements with different data types**.

Example:

<img src="https://github.com/AlproITS/DasarPemrograman/blob/master/img/struct.PNG" width="200px">

Look at the picture above. **Mahasiswa** is an entity in which there are attributes, namely:
   + Nama
   + NRP
   + Umur
   + IPK
   + Semester
   + Status

These attributes are members of the `Mahasiswa` struct.

### Struct Declaration

Like variables, structs must be declared before it can be used. The struct declaration uses the following syntax.
```c
struct <struct_name> {
    <member_data_type> <member_name>;
    <member_data_type> <member_name>;
    <member_data_type> <member_name>;
    .
    .
    .
};
```

Below is an example of a struct declaration based on the Mahasiswa case above.

```c
struct Mahasiswa {
    char nama[100];
    char nrp[20];
    int umur;
    double ipk;
    int semester;
    int status;
};
```

### Struct Variables

Once declared, a struct will become a new data type. So in this case, the Mahasiswa struct here becomes a new data type with the members being `nama`, `nrp`, `umur`, `ipk`, `semester`, and `status`. Here is how we create struct variables.

```c
struct <struct_name> <variable_name>;
```

Example:
```c
struct Mahasiswa mhs1;
struct Mahasiswa mhs2;
```

The example above shows that there are two variables mhs1 and mhs2 of type struct `Mahasiswa`.

### Access Struct Members

How do we access the members of the struct variables that have been created? To access the members of a struct, use the dot operator (.) after the variable name.

```c
<variable_name>.<struct_member_name>
```

Example:
```c
mhs1.umur = 19;
mhs1.semester = 3;

mhs2.umur = 20;
mhs2.semester = 5;
```

Sample program to demonstrate Struct:
```c
#include <stdio.h>
#include <string.h>

struct Mahasiswa {
    char nama[100];
    char nrp[20];
    int umur;
    double ipk;
    int semester;
    int status;
};

int main(void)
{
    struct Mahasiswa mhs1;

    strcpy(mhs1.nama, "Ahmad");
    strcpy(mhs1.nrp, "05111940000012");
    mhs1.umur = 18;
    mhs1.ipk = 3.94;
    mhs1.semester = 3;
    mhs1.status = 1;

    printf("Nama\t: %s\n", mhs1.nama);
    printf("NRP\t: %s\n", mhs1.nrp);
    printf("Umur\t: %d\n", mhs1.umur);
    printf("IPK\t: %.2lf\n", mhs1.ipk);
    printf("Sem\t: %d\n", mhs1.semester);
    printf("Status\t: %s\n", (mhs1.status == 1 ? "Active" : "Not Active"));
    
    return 0;
}
```

### Array of Struct

We can also create arrays with the struct data type. The method is exactly the same as most array declarations.

```c
#include <stdio.h>
struct Point {
    int x, y;
};

int main()
{
    struct Point arr[3];
    arr[0].x = 2, arr[0].y = 3;
    arr[1].x = 5, arr[1].y = 3;
    arr[2].x = 2, arr[2].y = 8;

    printf("%d %d\n", arr[0].x, arr[0].y);
    printf("%d %d\n", arr[1].x, arr[1].y);
    printf("%d %d\n", arr[2].x, arr[2].y);
    
    return 0;
}
```