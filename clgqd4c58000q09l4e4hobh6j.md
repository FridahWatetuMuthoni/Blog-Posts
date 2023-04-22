---
title: "Creating a Simple Calculator in C using structs and function pointers"
seoTitle: "Creating a Simple Calculator in C using structs and function pointers"
seoDescription: "Creating a Simple Calculator in C using structs and function pointers"
datePublished: Fri Apr 21 2023 09:42:01 GMT+0000 (Coordinated Universal Time)
cuid: clgqd4c58000q09l4e4hobh6j
slug: creating-a-simple-calculator-in-c-using-structs-and-function-pointers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682069963357/9298450f-a147-4eff-a2a2-34d528845e48.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1682070107732/62d51700-ced3-4706-a673-d515c4a18adc.jpeg
tags: c, pointers, pointers-in-c, calculator, structs-in-c

---

<iframe src="https://www.thiscodeworks.com/embed/644258d310dff000135bdb8f" style="width:100%;height:1295px"></iframe>

This is a C program that performs basic arithmetic calculations based on the command line arguments provided to it. The program takes three command line arguments, the first and third arguments are the two operands, and the second argument is the operator sign.

The program includes two header files, `stdio.h` and `stdlib.h`. The `stdio.h` header file provides functions for input and output, such as `printf()` and `scanf()`. The `stdlib.h` header file provides functions for memory allocation, conversion of string to numbers, and other miscellaneous functions.

The program starts by defining five functions that perform basic arithmetic operations: `add()`, `subtract()`, `multiply()`, `division()`, and `module()`. These functions take two integer arguments and return the result of the corresponding operation. These functions are declared before they are used, which is done through function prototypes.

Next, a `calc_t` struct is defined to create a sign and the associated function. This struct contains two members: `sign` which is a character pointer that holds the arithmetic operator, and `func` which is a function pointer that points to the corresponding arithmetic function. The `typedef` keyword is used to define this struct as `calc_t` for convenience.

The `main()` function is defined which takes two arguments: `argc` and `argv`. The `argc` parameter is the number of command line arguments, and `argv` is an array of character pointers that contains the command line arguments passed to the program. The function returns an integer value of 0 on success.

In the `main()` function, a variable `i`, `num1`, `num2`, `len`, `result`, and `sign` are defined. `num1` and `num2` are assigned the first and third command line arguments respectively. `sign` is assigned the second command line argument, which is the arithmetic operator.

The arithmetic operator sign and corresponding functions are defined in the `calc_t` struct. The `len` variable is assigned the size of the `calc_t` array divided by the size of a single `calc_t` element.

The program uses a `while` loop to iterate over the `calc_t` array. If the arithmetic operator `sign` matches with any of the operator signs in the `calc_t` array, then the corresponding arithmetic function is called with `num1` and `num2` as arguments, and the result is stored in the `result` variable. The `printf()` function is used to print the result.

Finally, the `main()` function returns 0 on successful completion.

In summary, this program performs basic arithmetic calculations on two operands based on the arithmetic operator passed as a command line argument. It makes use of function pointers, a `typedef` struct, and command line arguments.

For the multiplication function to work pass the multiplication sign like this "\*"

`>> gcc calculator.c -o calc`

`>> ./calc 5 "*" 5`

`>> ./calc 5 / 5`

`>> ./calc 10 + 5`

`>> ./calc 10 % 8`

`>> ./calc 6 - 2`