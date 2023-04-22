---
title: "How to Print an Integer Using the putchar() function"
seoTitle: "How to Print an Integer Using the putchar() function"
seoDescription: "How to Print an Integer Using the putchar() function"
datePublished: Sat Apr 22 2023 10:48:39 GMT+0000 (Coordinated Universal Time)
cuid: clgruxvtw000r09l37lgi66f5
slug: how-to-print-an-integer-using-the-putchar-function
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682160410943/df49eac5-56af-4962-b07f-58d2eae6a10a.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1682160500757/bb3a8593-d63f-4436-ba9b-d8b7f3190acd.jpeg
tags: c, programming-blogs

---

<iframe src="https://www.thiscodeworks.com/embed/6443ba537c7f610013784566" style="width:100%;height:476px"></iframe>

This is a C program that defines a function named `print_number()` which takes an integer value as a parameter and prints it to the console. It also has a `main()` function which calls the `print_number()` function with the integer value 1028 as an argument.

Let's take a closer look at the code:

```c
#include <stdio.h>
```

This line includes the standard input/output header file which contains functions for input and output operations.

```c
void print_number(int num)
```

This line defines a function named `print_number()` which takes an integer value `num` as a parameter and does not return a value (i.e., it has a `void` return type).

```c
unsigned int number;
```

This line declares an unsigned integer variable named `number`.

```c
if (num < 0)
{
    number = -num;
    putchar('-');
}
else
{
    number = num;
}
```

This code block checks if the value of `num` is negative. If `num` is negative, it takes the absolute value of `num` and stores it in `number`, and then it prints a minus sign to the console. If `num` is not negative, it simply assigns the value of `num` to `number`.

```c
if (number / 10)
{
    print_number(number / 10);
}
putchar('0' + (number % 10));
```

This code is a recursive function that prints out the digits of a positive integer number in reverse order. Here's how it works:

* The function takes in an integer `number` as its argument.
    
* The condition `if (number / 10)` is the same as `if (n / 10 != 0)`. In other words, the body of the `if` statement will execute as long as `n / 10` is not zero
    
* Inside the curly braces, the function calls itself recursively with `print_number(number / 10)`. This means that the function is called again with `number` divided by 10. This will continue until `number` becomes less than 0 or 0, at which point the condition will evaluate to false, and the recursive calls will stop.
    
* After the recursive calls have stopped, the function executes `putchar('0' + (number % 10))`. This prints out the last digit of the original `number` by taking the remainder of `number` divided by 10, and adding it to the ASCII code of the character '0'. This converts the digit to its corresponding ASCII code and prints it out as a character.
    
* Because the recursive calls were made in reverse order, the digits are printed out in reverse order as well.
    

For example, if we call the function with `number` equal to 123, the following steps will occur:

1. `if (123 / 10)` evaluates to true, the function calls itself with `print_number(12)`.
    
2. `if (12 / 10)` evaluates to true, the function calls itself with `print_number(1)`.
    
3. `if (1 / 10)` evaluates to false, the function does not call itself again.
    
4. `putchar('0' + (1 % 10))` prints out the character '1'.
    
5. The function returns to the previous call with `number` equal to 12.
    
6. `putchar('0' + (12 % 10))` prints out the character '2'.
    
7. The function returns to the initial call with `number` equal to 123.
    
8. `putchar('0' + (123 % 10))` prints out the character '3'.
    
9. The function exits.
    

Thus, the output of calling `print_number(123)` would be "321".

```c
int main(void)
{
    int num = 1028;
    print_number(num);
    putchar('\n');
    return (0);
}
```

This is the main function of the program. It declares an integer variable named `num` and assigns it the value 1028. It then calls the `print_number()` function with `num` as the argument to print the value of `num` to the console. Finally, it prints a newline character to the console using `putchar('\n')` and returns 0 to indicate successful program completion.