---
title: "Reversing a String In C"
datePublished: Tue Apr 18 2023 11:02:47 GMT+0000 (Coordinated Universal Time)
cuid: clgm5onhj000209l96jfph01f
slug: reversing-a-string-in-c
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1681815673578/e7304134-dd9b-4330-863d-65d01f6856f2.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1681815749935/89ebf289-e7da-420b-8034-06e966cbad77.jpeg
tags: c, programming-blogs, programming-tips, string-methods, strings-and-methods

---

<iframe src="https://www.thiscodeworks.com/embed/643e77a042e8de00130a6e4d" style="width:100%;height:554px"></iframe>

This C program defines two functions to reverse a given string:

1. `_strlen(char *str)`: calculates the length of a string `str`.
    
2. `reverse_string(char *str)`: reverses the string `str` by swapping its characters.
    

The `main` function uses `reverse_string` to reverse the string `"JQK"` and prints the result to the console.

Here's a step-by-step breakdown of what the program does:

1. The `_strlen` function takes a string `str` as input and returns its length as an integer. It does this by initializing a variable `len` to 0, then iterating over the characters in `str` with a for loop until it reaches the null character (`'\0'`). For each character, it increments `len` by 1. Finally, it returns `len`.
    
2. The `reverse_string` function takes a string `str` as input and modifies it in place to reverse its characters. It does this by first calling `_strlen` to determine the length of `str`. It then initializes two variables, `i` and `j`, to the beginning and end of the string, respectively. It then iterates over the string with a for loop, swapping the characters at positions `i` and `j` until `i` and `j` meet in the middle of the string. It uses a temporary variable `temp` to hold one of the characters during the swap.
    
3. In the `main` function, a string `str` containing the characters "JQK" is defined. The `reverse_string` function is then called with `str` as its input, which modifies `str` in place to reverse its characters. Finally, the reversed string is printed to the console using `printf`.
    

The output of the program will be:

```plaintext
Reversed string: KQJ
```