---
weight: 3
title: "Binary Numbers"
---

# Binary Numbers

In this chapter we are going to implement methods that help us work with binary numbers. First we are going to read binary numbers as strings from STD input stream, and then we are going to validate these strings to make sure that the input is actually a binary number. After that we will be able to do more fun stuff, such as converting a binary number to a decimal and vice versa, and more.

---

#### Required knowledge

In order to be able to complete this practice we will assume that you are familiar with core programing concepts [variables](), [std in / out](), [data types](), [data types conversion](), [flow-control](), [loops](), [arrays](), [static methods]() and that you have acquired at least very basic algorithmic thinking and problem solving mindset. For this particular practice we will also assume that you have read the corresponding theory [Number]() and [Binary Number System]().

---

The problems that we are going to solve here will serve as a starting point for later more complex OOP implementation of a library that will allow us to work with binary numbers. More complex practice regarding binary numbers can be found [here](/docs/problems/oop/binary/).

## Tasks

**[1]** Write a static method called `IsValidBinary` that takes an argument of type `string` and verifies that the given string is actually a valid representation of a binary number. Method returns either `true` or `false`. Examples:

```
1010 -> true
1111 -> true
1121 -> false
11b0 -> false
0000 -> true
```

**[2]** Write a static method called `ParseBinary` that takes an argument of type `string` and converts the gien binary number into a decimal number. Make sure that the given argument is actually a binary number, in case it isn't, method should return `-1`. Examples:

```
0000 -> 0
0001 -> 1
0010 -> 2
0011 -> 3
0100 -> 4
1000 -> 8
0012 -> -1
00b0 -> -1
```
