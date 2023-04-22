---
title: "A Function that Implements the strcmp() Function that Copies the Contents of one string to another"
seoTitle: "A Function that copies one str to another in C"
seoDescription: "A Function that Implements the strcmp() Function that Copies the Contents of one string to another"
datePublished: Tue Apr 18 2023 10:41:24 GMT+0000 (Coordinated Universal Time)
cuid: clgm4x5s1000p09mf3utue154
slug: a-function-that-implements-the-strcmp-function-that-copies-the-contents-of-one-string-to-another
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1681814357095/daaa69be-e416-43c4-abef-13fa977b672f.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1681814423836/b2be2919-bd3f-4161-aeab-79fdcec49b5a.jpeg
tags: c, programming-blogs, strings, programming-tips, strings-and-methods

---

<iframe src="https://www.thiscodeworks.com/embed/643e724142e8de00130a6e4a" style="width:100%;height:541px"></iframe>

This program demonstrates the use of a custom function `_strcpy()` to copy a string from one array to another.

In the `main()` function, two character arrays `str1` and `str2` of size 20 are defined. `str1` is initialized with the string "Hello".

The `_strcpy()` function is then called with arguments `str2` and `str1`. This function takes two arguments: a destination string `dest` and a source string `src`. It copies the characters from the source string `src` to the destination string `dest` and returns a pointer to the destination string.

The `ptr` pointer in `main()` is assigned the return value of `_strcpy()` which is the address of the `str2` array.

Finally, the program prints the contents of `str1` and `str2` using `printf()` function.

When this program is run, it will output the following:

```plaintext
str1: Hello
str2: Hello
```

This is because `_strcpy()` function copies the string "Hello" from `str1` to `str2`, and the pointer `ptr` points to the beginning of `str2` where the string "Hello" is copied.