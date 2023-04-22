---
title: "Understanding Structs and Memory Allocation in C: A Comprehensive Guide with Example Code"
seoTitle: "Structs, Pointers and Memory Allocation in C"
seoDescription: "The use of structs, dynamic memory allocation with malloc and free functions, as well as string manipulation functions such as _strlen and _strcpy."
datePublished: Tue Apr 18 2023 12:10:00 GMT+0000 (Coordinated Universal Time)
cuid: clgm833ib00090amjdwv94v2x
slug: understanding-structs-and-memory-allocation-in-c-a-comprehensive-guide-with-example-code
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1681819423447/ae888414-2ebe-4d92-ac44-0e56bdb7541b.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1681819381691/56952396-b45d-41ae-9124-750346b3e8be.jpeg
tags: c, programming-blogs, dynamic-memory-allocation, struct, pointers-in-c

---

<iframe src="https://www.thiscodeworks.com/embed/643e865242e8de00130a6e55" style="width:100%;height:1919px"></iframe>

This code defines a struct for a dog, creates a new dog using a function, and then frees the memory used by the dog using another function.

The struct named `dog` defines the information that a dog should have, which includes the dog's name, age, and owner's name. A typedef statement is used to create a new type called `dog_t` that can be used in place of the struct `dog`.

The code then defines three functions: `new_dog()`, `_strlen()`, and `_strcpy()`.

`_strlen()` takes a string as input and calculates its length by iterating through each character in the string and incrementing a counter. It returns the length of the string.

`_strcpy()` takes two strings as input and copies the contents of the second string into the first string. It does this by iterating through each character in the second string and copying it into the corresponding position in the first string. The function then adds a null terminator at the end of the copied string and returns a pointer to the destination string.

`new_dog()` creates a new dog using the input provided. It takes the name, age, and owner's name as arguments and checks to make sure that the name and owner's name are not null pointers, and that the age is greater than or equal to zero. It returns null if any of these conditions are not met. Otherwise, it allocates memory for a new `dog_t` struct using the `malloc()` function. If memory allocation is unsuccessful, it returns null. If successful, it then allocates memory for the name and owner using `malloc()` based on their length, then uses `_strcpy()` to copy the input name and owner into the allocated memory. Finally, it sets the dog's age and returns a pointer to the new dog.

`free_dog()` takes a pointer to a `dog_t` struct as input and frees the memory allocated for the struct's name, owner, and the struct itself. It first checks to see if the input pointer is null and returns if it is. Otherwise, it frees the memory allocated for the name, owner, and then the struct itself using the `free()` function.

The `main()` function demonstrates how to use the `new_dog()` and `free_dog()` functions. It creates a new dog named "Poppy" with an age of 3.5 and an owner named "Bob", prints out the dog's name and age, and then frees the memory used by the dog.