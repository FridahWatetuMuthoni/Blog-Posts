---
title: "A Function that Implements the strstr() function to search for a substring in a string"
seoTitle: "function to implement strstr() in C"
datePublished: Tue Apr 18 2023 09:49:11 GMT+0000 (Coordinated Universal Time)
cuid: clgm3207v00010alagw3h2ezf
slug: a-function-that-implements-the-strstr-function-to-search-for-a-substring-in-a-string
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1681811174220/012953a7-ce31-4682-993d-171561429a85.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1681811291125/a4ab7d92-3b1f-4d38-84fd-c3f38d0a1573.jpeg
tags: c, programming-blogs, string, strings-and-methods

---

<iframe src="https://www.thiscodeworks.com/embed/643e65c242e8de00130a6e3f" style="width:100%;height:800px"></iframe>

The given code implements the `_strstr` function that searches for a given substring `needle` in the main string `haystack` and returns the pointer to the first occurrence of the given substring in the main string.

The function first initializes two variables `i` and `j` for iterating through the `haystack` and `needle` strings respectively. Then it starts two nested loops for checking each character of the `haystack` and `needle` strings. If a character in `haystack` does not match the corresponding character in `needle`, the inner loop is broken and the outer loop continues with the next character in `haystack`. Otherwise, if the loop completes without any breaks, it means that the entire `needle` substring has been found in `haystack`. In that case, the function sets the pointer `start` to the address of the current character in `haystack` and returns it.

The `main` function uses the `_strstr` function to search for the substring `"weather"` in the string `"Hello, how's the weather today?"`. It then prints the result depending on whether the substring was found or not.