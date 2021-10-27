---
weight: 2
title: "Arrays"
math: true
---

# Arrays

In this practice we are going to cover some of the most often used algorithms to read, filter and transform the array according to our needs. We will assume that you already understand how arrays work, but a small reminder will be written here in the document.

We will start simple, and slowly work our way to more complex stuff. Once you are ready you can checkout more advanced practice [here]().

---

#### Required knowledge

In order to be able to complete this practice we will assume that you are familiar with core programing concepts [variables](), [std in / out](), [data types](), [data types conversion](), [flow-control](), [loops](), [arrays](), [static methods]() and that you have acquired at least very basic algorithmic thinking and problem solving mindset.

---

## Recollection

Let us recall the basics of how we work with the arrays. In the beginner practice we will keep things simple, and we will always work with simple types like `int`, `char`, `string`. Later on, we will also work with more complex user defined types (classes).

To declare an array of ints of size 10 we write

```csharp
int[] arr = new int[10];
```

In order to access the elements of the array we need to use `index`. First elemnent of the array has index 0, as arrays are indexed from `0` to `length - 1`.

```csharp
arr[0] = 13; // -> assigns the first element of the array to be 13
Console.WriteLine(arr[0]); // -> prints the first element of the arr
```

We can also declare an array by giving it elemnents rightaway:

```csharp
int[] arr = new int[] { 1, 2, 3, 4, 5 }; // Will create an array of size 5, with the given elements
```

In order to acccess all elements more easily, we usually use loops. The following program prints all elements of the array

```csharp
for (int i=0; i<arr.length; i++)
{
    Console.WriteLine(arr[i]);
}
```

We can also use `while` loop

```csharp
int index = 0;
while (index < arr.length)
{
    Console.WriteLine(arr[index]);
    index++;
}
```

## Tasks

<details>
<summary>[1] Printing the arrays</summary>

**[1.1]** Write a static method `PrintArrLn` that takes one argument an array of integers and prints the elements of the array. For the array `[1, 2, 3, 4, 5]` the method prints

```
1
2
3
4
5
```

**[1.2]** Write a static method `PrintArrHr` that takes one argument an array of integers and prints the elements of the array. For the array `[1, 2, 3, 4, 5]` the method prints

```
1 2 3 4 5
```

**[1.3]** Write a static method `PrintArrHrRev` that takes one argument an array of integers and prints the elements of the array. For the array `[1, 2, 3, 4, 5]` the method prints

```
5 4 3 2 1
```

**[1.4]** Write a static method `PrintArrPretty` that takes one argument an array of integers and prints the elements of the array. For the array `[1, 2, 3, 4, 5]` the method prints

```
[1, 2, 3, 4, 5]
```

**[1.5]** Write a static method `PrintArrRight` that takes one argument an array of integers and prints the elements of the array. For the array `[1, 2, 3, 4, 5]` the method prints

```
1
  2
    3
      4
        5
```

**[1.6]** Write a static method `PrintArrLeft` that takes one argument an array of integers and prints the elements of the array. For the array `[1, 2, 3, 4, 5]` the method prints

```
        1
      2
    3
  4
5
```

**[1.7]** Write a static method `PrintArrBin` that takes one argument an array of integers and prints the elements of the array.

For the array `[1, 2, 3, 4, 5]` the method prints

```
1 5 2 4 3
```

For the array `[1, 2, 3, 4]` the method prints

```
1 4 2 3
```

For the array `[1, 2, 3]` the method prints

```
1 3 2
```

</details>

<details>
<summary>[1.1] Searching the arrays</summary>

**[1.1.1]** Write a static method `Exists` that takes an array of integers and an element `e` and searches for the element in the array. If the element exists it should return `true`, otherwise `false`.

```
([1, 2, 3, 4, 5], 2) -> true
([1, 2, 3, 4, 5], 1) -> true
([1, 2, 3, 4, 5], 7) -> false
([1, 2, 3, 4, 5], 4) -> true

```

**[1.1.2]** Write a static method `Contains` that takes an array of integers and an element `e` and searches for the element in the array. If the element is found it should return its position, otherwise `-1`.

```
([1, 2, 3, 4, 5], 2) -> 1
([1, 2, 3, 4, 5], 1) -> 0
([1, 2, 3, 4, 5], 7) -> -1
([1, 2, 3, 4, 5], 4) -> 3

```

</details>

<details>
<summary>[2] Modifying the arrays</summary>

**[2.1]** Write a static method `AddOneToEach` that takes an array of integers and adds `1` to every element. Print the array before and after to confirm that your method worked correctly. For the array `[1, 2, 3]` it should print `[2, 3, 4]`.

**[2.2]** Write a static method `MultEachBy` that takes an array of integers and an integer `x` and multiplies each element of the array by `x`. Method should print the multiplied array. Example

```
In:
[1, 2, 3], 2
Out:
[2, 4, 6]
```

**[2.3]** Write a static method that takes an array of integers `DivEachBy` and an integer `d` and divides each element of the array by that integer. If `d = 0` method should print the correct 'division by zero' error message, otherwise, print the modified array.

```
In:
[2, 4, 6], 2)
Out:
[1, 2, 3]

In
[1, 2, 3], 0
Out:
ERR: division by zero.
```

</details>

<details>
<summary>[3] Sums, Products </summary>

So far our methods were taking the arrays, doing some modification, and we were expecting them just to print the result. In programming we usually do things a little different, we usually do not want to have methods print stuff, and modify stuff directly, but rather we want them returning the expected results. In this section we will change the approach a little bit. You will understand more why we do this in the advanced [practice]().

Let's recall some math theory about sums and products. The following formula is a way to write a sum of all the elements between i and n.

$$
\sum\_{i=0}^{n} i
$$

Likewise, this formula is a product of all elements between i and n

$$
\prod\_{i=1}^{n} i
$$

But this is just a fancy, mathematical way to write a sum and product. All this says is that `i` is a variable which starts from 0 for sum or 1 for product, that has all the values from that start value up to `n` and all these values add or multiply to get the final result. Although this is fairly simple, and there is a detailed explanation in the [numbers]() under Math, we can still observe examples.

**[E1]** Sum from 0 to 5

$$
\sum\_{i=0}^{5} i = 0 + 1 + 2 + 3 + 4 + 5
$$

and likewise

**[E2]** Product from 1 to 5

$$
\sum\_{i=1}^{5} i = 1 * 2 * 3 * 4 * 5
$$

finally let us move to some tasks.

**[3.1]** Write a static method `ArrSum` that takes an array of integers and computes the sum of the elements of that array, it should return the result. For example

```
[1, 2, 3]   -> 6
[ ]         -> 0
[1]         -> 1
```

**[3.2]** Write a static method `ArrProd` that takes an array of integers and computes the product of the elements of that array, it should return the result. For example

```
[1, 0, 3]   -> 0
[ ]         -> 1
[1]         -> 1
[1, 2, 3]   -> 6
```

**[3.3]** Write a static method `ArrSumEven` that takes an array of integers and computes the sum of all even numbers of that array, it should return the result. For example

```
[1, 0, 3]   -> 0
[ ]         -> 0
[1]         -> 0
[1, 2, 3]   -> 2
[2, 2, 2]   -> 6
```

**[3.4]** Write a static method `ArrSumNonEven` that takes an array of integers and computes the sum of all non-even numbers of that array, it should return the result. For example

```
[1, 0, 3]   -> 4
[ ]         -> 0
[1]         -> 1
[1, 2, 3]   -> 4
[2, 2, 2]   -> 0
```

</details>
