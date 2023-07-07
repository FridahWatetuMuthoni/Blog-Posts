---
title: "The Fibonacci Sequence using Recursion and Memoization without using a library in Python"
seoTitle: "The Fibonacci Sequence using Recursion and Memoization"
seoDescription: "The Fibonacci Sequence using Recursion and Memoization without using a library in Python"
datePublished: Fri Jul 07 2023 11:49:17 GMT+0000 (Coordinated Universal Time)
cuid: cljsiklok000209l6dlbt9e25
slug: the-fibonacci-sequence-using-recursion-and-memoization-without-using-a-library-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688730405966/fdfc41a3-bb4f-4075-aa23-ffb2a7f24d8e.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1688730519586/21eac7fd-441c-4212-b9de-dfa211cf0ef0.jpeg
tags: recursion, memoization, fibonacci, fibonacci-sequence

---

<iframe src="https://www.thiscodeworks.com/embed/64a7f53e7bfaf3001377cf1f" style="width:100%;height:520px"></iframe>

The Fibonacci sequence is a famous mathematical sequence where each term is the sum of the two preceding terms. In this blog post, we will walk through a Python code that calculates the Fibonacci sequence and explain each step in detail.

Step 1: Initializing the Cache

The code begins by creating an empty dictionary called `fibonacci_cache`. This dictionary will be used to store the results of previously computed Fibonacci numbers, allowing us to avoid redundant calculations and improve performance.

Step 2: Defining the Fibonacci Function

Next, we define a function called `fibonacci(n)` that takes an integer `n` as its input and returns the nth Fibonacci number. This function will be recursively called to calculate Fibonacci numbers.

Step 3: Input Validation:

The function checks if the input 'n' is an integer using `type(n) != int`. If it is not, a `TypeError` is raised.

It also checks if the input 'n' is a positive integer using `(n < 1)`. If not, a `ValueError` is raised.

Step 4: Checking the Cache

Inside the `fibonacci` function, we first check if the result for the given value of `n` is already present in the cache. If it is, we can immediately return the cached value, avoiding unnecessary computations. This step helps in optimizing the function by reducing redundant calculations.

Step 5: Computing the Fibonacci Number

If the result is not in the cache, we proceed to compute the Fibonacci number for the given `n`. The code uses a series of conditional statements to handle the base cases of `n = 1` and `n = 2`, where the Fibonacci numbers are both 1. For `n` greater than 2, the code uses recursion to calculate the sum of the (n-1)th and (n-2)th Fibonacci numbers, as per the definition of the Fibonacci sequence.

Step 6: Caching the Result

Once the Fibonacci number for the given `n` is computed, we store the result in the `fibonacci_cache` dictionary using `fibonacci_cache[n] = value`. This ensures that we have the result available in the cache for future use.

Step 7: Returning the Result

Finally, we return the computed Fibonacci number `value` from the `Fibonacci` function.

Step 8: Printing the Fibonacci Sequence

In the subsequent loop, the code iterates from 1 to 100 (inclusive) and prints each number in the Fibonacci sequence. It achieves this by calling the `fibonacci` function for each value of `n` and printing the result.

Conclusion: This Python code demonstrates an efficient way to calculate the Fibonacci sequence by utilizing caching. By storing previously computed values in a cache, redundant calculations are avoided, leading to improved performance. Understanding each step of the code helps demystify the process of generating Fibonacci numbers and showcases the power of recursion and caching in solving mathematical problems.