---
aliases: ["1.1 - Prologue: The Problem of Measure", "Ch 1.1 - Prologue: The Problem of Measure"]
created: 2023-11-12T18:40:35-08:00
modified: 2023-11-13T21:06:47-08:00
tags: 
---
# 1.1 - Prologue: The Problem of Measure
- For instance, in one dimension, the intervals $A := [0, 1]$ and $B := [0,2]$ are in one-to-one correspondence (using the bijection $x \rightarrow 2x$ from $A$ to $B$), but of course $B$ is twice as long as $A$. So one can disassemble $A$ into an uncountable number of points and reassemble them to form a set of twice the length.
	- This is the most concise explanation of the Banach Tarski paradox I have ever seen. [[folland1999real-Ch1]] §1.1 left me confused about this
- An elementary set is any subset of $\mathbb{R^d}$ which is the union of a finite number of boxes
	- [[Q::How does this relate to the notion of an elementary family in Folland?]]

# 1.3 - The Lebesgue Integral
- Lebesgue theory is a completion of the Riemann theory of integration.
- We first define the Lebesgue integral for simple functions
- We follow by defining the Lebesgue integral for non-negative functions $f:\mathbb{R^d} \rightarrow [0,\infty]$
- Then we consider unsigned functions to define absolutely convergent Lebesgue integrals.

Some motivation for the Lebesgue integral from the theory of infinite sums. Consider an infinite sum, and recall that we can rearrange the terms and always get the same result if it is absolutely convergence. Similarly, we want to define a notion of absolute convergence for the Lebesgue integral since we aim to be able to break up the integral into sums of the measures of the domain with the same value kinda. For the case where elements of the sum are unsigned, we can express the sum as a supremum of partial sums. Signed infinite sums can then be broken into unsigned sums via their positive and negative parts.
