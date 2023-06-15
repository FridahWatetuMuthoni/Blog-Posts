---
title: "Reversing a String In Python Using Recursion"
datePublished: Thu Jun 15 2023 11:10:18 GMT+0000 (Coordinated Universal Time)
cuid: clix1hq02000v0al7ghnb5l90
slug: reversing-a-string-in-python-using-recursion
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686827210307/0b866361-2e61-4829-8c91-177c19a645c4.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1686827326165/c916993c-803a-4ea6-9323-a4621a383f9e.jpeg
tags: python, python-string, recursion-in-python

---

<iframe src="https://www.thiscodeworks.com/embed/648aee69c07e5c001347c290" style="width:100%;height:250px"></iframe>

Here's a step-by-step breakdown of how the function works:

1. The function `reversing_string()` takes a string as input.
    
2. It checks if the input string is empty (`""`). If it is, an empty string is returned as the base case of the recursion.
    
3. If the input string is not empty, the function makes a recursive call to `reversing_string()` with the argument `string[1:]`. This slices the input string from the second character onward and passes it as an argument to the recursive call.
    
4. The function continues to make recursive calls until it reaches the base case (an empty string).
    
5. Once the base case is reached, the function starts returning the reversed string by appending `string[0]` (the first character of the original string) to the reversed version of the remaining substring.
    
6. The recursion unfolds, and each recursive call appends the characters from the original string in reverse order until the complete reversed string is built.
    
7. The final reversed string is assigned to the variable `str`.
    
8. Finally, the reversed string is printed.
    

If you run this code, it will output:

```python
dlroW olleH
```

How this line works: `reversing_string(string[1:]) + string[0]`

```python
Hello World
ello World
llo World
lo World
o World
 World
World
orld
rld
ld
d
```