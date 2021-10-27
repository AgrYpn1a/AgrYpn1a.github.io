---
weight: 1
title: "Arrays"
math: true
bookFlatSection: true
---

# Arrays

This practice assumes that you have completed the beginner array [practice]({{< relref "/docs/problems/beginner/arrays">}}). We are going to write a class that is like a library that allows us to work with arrays in a very useful way.

In this practice, we are going to assume that you are familiar with some basics of [functional]() programming, as our approach to solving the problems given here will be functional-oriented. This means that do NOT want to modify the given inputs in any way, and always instead return the modified input from the function. This also means no `void-type` functions anymore. All functions (methods) will be static.

So let's begin by jumping right into it, and write the first useful method that copies the array and returns that copy.

> Note: we will assume that our methods work with integers only for the sake of simplicity.

**[1.0a]** Write a new class called `CSArrays` and in it write a static method called `Copy` that takes an array and creates a new one that is an exact copy of the given array. Method should return the newly created array copy.

**[1.0b]** Now let's extend this with another utility like method taht is generally useful. Write a static method `Reverse` that takes an array of integers and returns new array that is a reverse of the original.

```
[1, 2, 3] -> [3, 2, 1]
[1] -> [1]
```

---

> Note: we will assume that all methods work on copies of the input array. So use the `Copy` method that you have first written.
>
> > You do not need to make copies of the arrays that you are not going to modify. So for read operations such as `TakeFirst` and similar, you do not need to make copies first, this should be obvious at this point.

---

**[1.1]** Write a static method called `TakeFirst` that returns the first element of the array.

```
[ 13, 5, 6, 12, 5 ] -> 13
```

**[1.2]** Write a static method called `TakeLast` that returns the last element of the array.

```
[ 13, 5, 6, 12, 5 ] -> 5
```

**Now let us make things more complex.**

**[1.3]** Write a static method called `TakeFirstN` that takes an array and an integer `n` and returns the array with first `n` elements of the original array. Make sure to test against edge cases (they will be written as examples below).

```
([], 2) -> []
([2, 3, 6], 0) -> []
([1, 2], 5) -> [1, 2]
([1, 2, 3], -1) -> [] // ERR: n cannot be negative
([13, 2, 6, 14, 15], 3) -> [13, 2, 6]
```

<span style="color:red">**[1.4]**</span> Write a static method called `TakeLastN` that takes an array and an integer `n` and returns the array with last `n` elements of the original array. Make sure to test against edge cases (they will be written as examples below).

```
([], 2) -> []
([2, 3, 6], 0) -> []
([1, 2], 5) -> [1, 2]
([1, 2, 3], -1) -> [] // ERR: n cannot be negative
([13, 2, 6, 14, 15], 3) -> [6, 14, 15]
```

**[1.5]** Write a static method called `TakeEverySecond` that takes an array of integers and returns new array that contains every second element of the original array, starting with index 0 as first element.

```
[] -> []
[1] -> [1]
[1, 2] -> [1]
[1, 2, 3, 4] -> [1, 3]
[1, 2, 3, 4, 5] -> [1, 3, 5]
```

<span style="color:red">**[1.5]**</span> Write a static method called `TakeEveryNth` that takes an array of integers and an integer `n` and returns new array that contains every n-th element of the original array, starting with index 0 as first element.

```
([], 2) -> []
([1], 2) -> [1]
([1, 2], 3) -> [1]
([1, 2, 3, 4], 3) -> [1, 4]
([1, 2, 3, 4, 5, 6, 7, 8] , 3) -> [1, 4, 7]
```

At this point we are going to start writing some functions that are often used in functional paradigm. Many of the todays languages are functional or have a functional oriented extension. In web development we work with collections of data a lot, and we often use these functions, without maybe realising that this is a completely different paradigm. In order to use these well, we need to understand how they work first. In this practice we will stick with the more simpler approach and enter the functional world step by step. In the [expert]() arrays practice, we will implement this using higher-order functions, but for now we will work with specific cases and you will have to copy the same code all over again. This should also make you question this approach, and make you wonder if there is a way to reuse some parts of the code. When you are ready, proceed to the [expert]() practice to see how this is really done.

**[2.1]** In the previously defined `CSArrays` class, write a static method called `FilterPositive` that takes an array of integers and returns new array that consists of all positive integers of the original array.

```
[1, 2, -4, 5, -1, -16, 2] -> [1, 2, 5, 2]
```

**[2.2]** In the previously defined `CSArrays` class, write a static method called `FilterEven` that takes an array of integers and returns new array that consists of all even integers of the original array.

```
[1, 2, -4, 5, -1, -16, 2] -> [2, -4, -16, 2]
```

Now, we could make these a bit more general, so that we don't have a write a new function for every single usecase.

**[2.3]** In 2.1 you wrote a method `FilterPositive`, now write a new static method `FilterBySign` that takes an array of ints and an integer that can be 1 or -1. If it is 1 filter all positive elements otherwise all negatives.

```
([1, 2, -3, 12, -1, 3], 1) -> [1, 2, 3]
([1, 2, -3, 12, -1, 3], -1) -> [-3, -1]
```
