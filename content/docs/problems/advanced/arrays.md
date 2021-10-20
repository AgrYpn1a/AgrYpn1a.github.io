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

**[1.0]** Write a new class called `CSArrays` and in it write a static method called `Copy` that takes an array and creates a new one that is an exact copy of the given array. Method should return the newly created array copy.

---

> Note: we will assume that all methods work on copies of the input array. So use the `Copy` method that you have first written.
>
> > You do not need to make copies of the arrays that you are not going to modify. So for read operations such as `TakeFirst` and similar, you do not need to make copies first, this should be obvious at this point.

---

**[1.1]** Write a static method called `TakeFirst` that returns the first element of the array.

```
[ 13, 5, 6, 12, 5 ] -> 13
```

**[1.1]** Write a static method called `TakeLast` that returns the last element of the array.

```
[ 13, 5, 6, 12, 5 ] -> 5
```

**Now let us make things more complex.**

**[1.2]** Write a static method called `TakeFirstN` that takes an array and an integer `n` and returns the array with first `n` elements. Make sure to test against edge cases (they will be written as examples below).

```
([], 2) -> []
([2, 3, 6], 0) -> []
([1, 2], 5) -> [1, 2]
([1, 2, 3], -1) -> ERR: n cannot be negative
([13, 2, 6, 14, 15], 3) -> [13, 2, 6]
```
