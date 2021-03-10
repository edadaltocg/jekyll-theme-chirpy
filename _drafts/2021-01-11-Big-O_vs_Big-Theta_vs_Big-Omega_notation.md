---
layout: post
title: "Understanding algorithms: Big-O vs Big-Omega vs Big-Theta notation"
date: 2021-01-10 19:00:00 -0000
categories: Machine-Learning Algorithms
tags: complexity math big-O
math: true
---

In this article we will define and understand Big-O, Big-Omega and Big-Theta notation in the eyes of the developer. Their purpose is simple: to compare algorithms from a theoretical point of view, without the need to execute the code.

They are useful when comparing and describing algorithms and their practical meaning can be obscured behind complex mathematics. They also  come up often in technical interviews, so it’s key to familiarize yourself with the base concepts.

The goal of this article is to simplify and exemplify these concepts in the most practical way as possible.

TL;DR. [This comment](https://www.khanacademy.org/computing/computer-science/algorithms/asymptotic-notation/a/big-big-omega-notation) from Cameron summarizes it very well.

* if $f(n)$ is $O(g(n))$ this means that $f(n)$ grows no faster than $g(n)$.
* if $f(n)$ is $\Omega(g(n))$ this means that $f(n)$ grows no slower than $g(n)$.
* if $f(n)$ is $\Theta(g(n))$ this means that $f(n)$ grows at the same rate as $g(n)$.

# Big-O ($O$)

In formal terms, the big-O notation is used to describe an *asymptotic growth rate* with respect to one or several inputs.

> Big-O is known as the *worst case scenario* for an algorithm efficiency and is given as a tight *upper bound* to the worst execution.

So, the lesser the number of steps, the smaller the big-O and the faster the algorithm is.

**Why asymptotic?** Its value is calculated when the input size tends to *infinity*.

It represents a tight *upper bound* to the complexity of the worst execution. This means that an algorithm A with complexity $O(n^2)$, where $n$ is the input length, has also a complexity of $O(n^3)$, for example. But $O(n^2)$ is more restrictive than $O(n^3)$, thus we preserve the tighter bound for the algorithm A.

A restrictive, but useful definition is shown below.

$$
f(n)=O(g(n)) \text{ if there exists an integer } M \text{ such that } f(n)\leq Mg(n)
$$

This definition is enough when describing computer science algorithm's complexity.

## Examples


| Complexity    | Name        | Example                               |
| ------------- | ----------- | ------------------------------------- |
| $O(1)$        | Constant    | Addition, subtraction                 |
| $O(\log n)$   | Logarithmic | Binary search                         |
| $O(n)$        | Linear      | Simple search                         |
| $O(n \log n)$ | Loglinear   | Quicksort                             |
| $O(n^2)$      | Quadratic   | Selection sort                        |
| $O(n!)$       | Factorial   | Traveling salesperson via brute-force |

## How To Calculate Big-O of a script

Roughly, to calculate the Big-O of a piece of code you have to:

1. Break your code into individual components;
2. Calculate/search for the Big-O of each component;
3. Beware of nested and composite calculations;
4. Find the highest order term — this will be the resulting complexity of the script.

These properties below are useful when dealing with asymptotic functions and estimating the Big-O complexity of a script.

### Sum

$$
f_{1}=O\left(g_{1}\right) \text { and } f_{2}=O\left(g_{2}\right) \Rightarrow f_{1}+f_{2}=O\left(\max \left(g_{1}, g_{2}\right)\right)
$$

If your code looks like this:

```code
algorithm_a:
    component_1 (O(n))
    component_2 (O(log n))
```
Then the resulting Big-O complexity would be equal to:

$$
O(algorithm\_a) = O( \max \{ O(n) , O(\log n) \}) = O(n)
$$


Because the algorithm executes ```component_1``` *then* ```component_2```.

### Multiplication by a constant

$$
f=O(g) \Rightarrow k f=O(g)
$$

If your code looks like this:

```code
algorithm_a:
    execute k times:
        component_1 (O(n))
```

Then the resulting Big-O complexity would be equal to:

$$
O(algorithm\_a) = kO(n) = O(n)
$$

Note that $k$ here is a fixed constant that *does not* depends or grow with the input size $n$.  

### Product

$$
f_{1}=O\left(g_{1}\right) \text { and } f_{2}=O\left(g_{2}\right) \Rightarrow f_{1} f_{2}=O\left(g_{1} g_{2}\right)
$$


If your code looks like this:

```code
algorithm_a:
    for 1:n:
        component_2 (O(n))
        
```

```component_2``` is called $n$ times but it is itself a block of code with complexity $O(n)$. So, the resulting Big-O complexity for ```algorithm_a``` would be equal to:

$$
O(algorithm\_a) = O(n)O(n) = O(n^2)
$$

# Big-Omega ($\Omega$)

If you understood big-O, understanding Big-Omega is straight forward.

>Big-Omega is the *lower bound* of the complexity of an algorithm.

It is used to describe the time of execution of an algorithm without precising its upper bound. It is an *asymptotic lower bound* because it bounds the growth of the running time from below for large enough input sizes.

$$
f(n)=\Omega (g(n)) \text{ if there exists an integer } M \text{ such that } f(n)\geq Mg(n)
$$

## Examples


## Properties


# Big-Theta ($\Theta$)

Big-Theta states *both* asymptotic lower and upper bounds for the growth of a function. 

Mathematically,

$$
f(n)=\Theta (g(n)) \text{ if there exists integers } M_1 \text{ and } M_2 \text{ such that } M_1g(n) \leq f(x)\leq M_2g(n).
$$

> Hence, saying that the algorithm A is $\Theta(g(n))$ is the same as saying that A is both $O(g(n))$ *and* $\Omega(g(n))$.

## Examples


## Properties

# To keep in mind

When choosing the right computational algorithm to solve a problem, it is important to verify its memory and execution time complexity with the size of the input data. If you plan to solve problems that can scale very large, knowing $O(\cdot)$ of every piece of your code is mandatory. Inefficient algorithms can slow down your development process and may prevent your application to work.

Among the Bachmann–Landau notation explained in this article, Big-O is by far the most popular used to describe algorithms on articles and books. Understanding and incorporating it on your computational toolbelt will help you build more efficient and faster algorithms.

## Further reading

* Bachmann–Landau notation.
* Computational complexity theory.

## References

1. [Wikipedia article on Big-O notation](https://en.wikipedia.org/wiki/Big_O_notation).
2. [Khan Academy article](https://www.khanacademy.org/computing/computer-science/algorithms/asymptotic-notation/a/big-big-omega-notation)
3. [FreeCodeCamp article](https://www.freecodecamp.org/news/big-o-notation-simply-explained-with-illustrations-and-video-87d5a71c0174/).
4. [A practical medium article](https://medium.com/dataseries/how-to-calculate-time-complexity-with-big-o-notation-9afe33aa4c46).
5. [This thread from stackoverflow](https://stackoverflow.com/questions/3255/big-o-how-do-you-calculate-approximate-it?rq=1).
