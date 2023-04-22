---
title: "How to Print Multiple Data Types with a Single Function in C"
seoTitle: "How to Print Multiple Data Types with a Single Function in C"
seoDescription: "How to Print Multiple Data Types with a Single Function in C"
datePublished: Sat Apr 22 2023 06:45:33 GMT+0000 (Coordinated Universal Time)
cuid: clgrm99dz000d09jh73vb7g0l
slug: how-to-print-multiple-data-types-with-a-single-function-in-c
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682145776681/b67e7620-a3e6-40ff-9e5b-2fed2a3faf9d.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1682145910824/e01f68dd-4d3c-423b-9545-050a0dcd3055.jpeg
tags: c, pointers, struct, pointers-in-c, variadicfunctions

---

<iframe src="https://www.thiscodeworks.com/embed/6442843c10dff000135bdb9c" style="width:100%;height:1477px"></iframe>

This code is a C program that allows you to print any combination of strings, characters, integers and floats using a single function. The main idea of this program is to use variadic functions and a list of structs to identify the type of each argument and call the appropriate function to print it.

The program starts by including two standard C libraries: `stdio.h` and `stdarg.h` .The `stdio.h` library contains functions for input and output operations. The `stdarg.h` library provides facilities for functions that accept a variable number of arguments.

The program then declares four functions: `print_string`, `print_letter`, `print_integer` and `print_float`. These functions are used to print the corresponding data types. All these functions take a single argument of type `va_list`, which is a type that allows functions to accept a variable number of arguments.

Next, the program defines a structure named `print_t`. This structure contains two fields: `specifer`, which is a string that identifies the data type to be printed, and `print_func`, which is a pointer to the function that prints that data type. The program also defines an array of `print_t` structures named `functions`. This array contains four structures, one for each data type.

The program then defines a function named `print_all`. This function is the heart of the program, and it takes a variable number of arguments. The first argument is a format string, which is a string that contains specifiers for each argument that needs to be printed. The remaining arguments are the actual values that need to be printed.

Inside the `print_all` function, the program initializes a variable `i` to 0 and declares a pointer `separator` to an empty string. The `va_list` type variable `args` is then declared, and the function `va_start` is called to initialize `args` with the variable number of arguments passed to the function.

The function then loops through the format string to identify each data type. The program checks if the format string is not null and if the current character is not null.

Inside the loop, a variable `j` is initialized to zero. A nested loop then runs while `j` is less than the length of the `functions` array and the current character in `format` does not match the specifier in `functions[j].specifier`. This loop continues until a match is found or until the end of the `functions` array is reached.

If a match is found, the `print_func` function corresponding to the matched specifier is called with the `args` variable, which is a `va_list` object containing the values to be printed. The `printf` function is also called to print the `separator` string (initially an empty string, then a comma and a space after the first value is printed) between values.

After the inner loop completes, the variable `i` is incremented to move on to the next character in `format`.

At the end of the loop, a newline character is printed to separate the output from any subsequent text.

Overall, this loop reads through the `format` string and matches the specifiers with the appropriate print functions, printing out the corresponding values with the correct formatting.

After the loop is complete, the program prints a newline character and calls the `va_end` function to clean up the `args` variable.

The `main` function is defined next, which simply calls the `print_all` function with four arguments: a character, an integer, and a string.

Finally, the program defines the four functions used by the `print_all` function: `print_string`, `print_letter`, `print_integer` and `print_float`. Each of these functions takes a `va_list` argument, retrieves the next argument of the corresponding data type, and prints it to the standard output using the appropriate format specifier.