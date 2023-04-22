---
title: "A Function that Implements String Concatenation In C"
seoTitle: "A Function that Implements String Concatenation In C"
seoDescription: "A Function that Implements String Concatenation In C"
datePublished: Tue Apr 18 2023 11:30:46 GMT+0000 (Coordinated Universal Time)
cuid: clgm6omnc000109lbh3hj5swa
slug: a-function-that-implements-string-concatenation-in-c
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1681817331987/0c08bfbf-dcdc-45be-8032-92979edc0db7.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1681817409229/01be1b43-417e-4ee8-a598-eaa9904fd0f6.jpeg
tags: c, programming-blogs, programming-languages, strings-and-methods

---

<iframe src="https://www.thiscodeworks.com/embed/643e7e9f42e8de00130a6e54" style="width:100%;height:723px"></iframe>

This C program defines two functions: `_strlen` and `_strcat`. The `_strlen` function takes a string as input and returns its length. The `_strcat` function concatenates two strings and returns the resulting string. The `main` function demonstrates the use of the `_strcat` function.

The `_strcat` function takes two parameters: `dest` and `src`, which represents the destination and source strings, respectively. The function first finds the length of the destination string using the `_strlen` function. It then appends a space character to the end of the destination string and sets the index to the length of the destination string.

The function then uses a loop to concatenate the source string to the end of the destination string. It does this by copying each character of the source string to the destination string one by one. The loop continues as long as there are characters in both the destination and source strings.

Finally, the function adds a null character to the end of the concatenated string and returns a pointer to the destination string.

The `main` function creates two strings: `str1` and `str2`. It then calls the `_strcat` function with `str1` as the destination string and `str2` as the source string. It stores the resulting string in a pointer called `ptr` and prints it to the console.

When run, the program will output the concatenated string "Hello Word!".