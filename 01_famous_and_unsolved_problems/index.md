---
layout: lecture
title: Famous and Unsolved Problems
lecture: 1
date: February 3, 1999
transcriber: Wei-An Yu
---

1\. Self-Avoiding Random Walk
----------------------------

You start on the origin, $(0, 0)$, of a two-dimensional rectangular
coordinate system.  Toss a four-sided coin where all four sides have
equal probability of showing and each of the four sides corresponds to
a direction (either up/down/right/left or north/south/east/west).  The
probability of ever getting back to the origin is 1.  The
three-dimensional analogue is similar with a six sided coin
corresponding to up/down/left/right/forward/backward in a
three-dimensional rectangular coordinate system.  In the
three-dimensional case, the probability of ever returning to the
origin is approximately 0.3278.

Imagine a circular (or spherical in the 3-dimensional case) barrier of
radius $r$ centered at the origin.  What is the probability of hitting
the barrier in terms of $r$ and $n$ steps?  This problem is unsolved.

What is the probability that in the first $n$ steps, the random walk
will never return to a point it has visited?  This problem is
unsolved.  We do know that for $p_m$, the probability of a
self-avoiding $n$-step random walk, there exists $\lim_{n \rightarrow
\infty} \sqrt[n]{p_m}$.

2\. Pennies on a Carpet
----------------------

You have $n$ identical pennies and you drop them on a carpet (within
the carpet boundary).  What is the probability that no 2 pennies
overlap?  The solution is unknown.  In statistical mechanics, this
relates to the hard spheres problem.

3\. Cell Growth
--------------

Start with a single cell represented by a square.  Toss a four-sided
die with each side corresponding to the growth of a new cell (square).
Repeat this process $n$ times for the newly formed cell.  The
three-dimensional analogue replaces the square with a cube and uses a
six-sided die.  What is the general shape?  Do islands form?

4\. Cluster Analysis
-------------------

Imagine you have a large number of points of data plotted.  How do you
analyze the data, which may be multi-dimensional, into categories?
How could this be used in anomaly detection?  There are no direct
methods of solving this.  Current methods include solving indirectly,
inventing theories, etc.

The Grammar of Probability
--------------------------

We have the sample space, $\Omega$, whose elements, $\omega$, are
called sample points.  A family, $\varepsilon$, of subsets of
$\Omega$, is called an event, such that:

1. The null set, $\emptyset$, is an event.
2. If $A$ is an event, then its complement, $\Omega - A = A^c$, is
also an event.
3. If $A$ and $B$ are events, then $A \cap B$, the intersection of $A$
and $B$, is an event.
4. If $A_1, A_2, A_3, ...$ is a finite or infinite sequence of
disjoint events, then $A_1 \cup A_2 \cup A_3 \cup ...$, the union of
$A_1, A_2, A_3, ...$ is an event.

**Example 1.** If $\Omega$ is a finite set, every subset of $\Omega$ is an event.

**Example 2.** The Bernoulli Process:

$$
\begin{eqnarray*}
\Omega &=& \{ \omega = (\omega_1, \omega_2, \omega_3, ...)\}, \; \omega_n = \text{0 or 1}\\
\varepsilon :\: H_n &=& \text{event that $n$th toss is head}\\
&=& \text{the set of all sample points $\omega$} = (\omega_1, \omega_2, ..., \omega_n, \omega_{n + 1}, ...)\\
&&\text{ for which $\omega_n = 1$.}\\
\end{eqnarray*}
$$



Any subset of $\Omega$ obtainable from any of the $H_n$ by successive
aplication of 1, 2, 3, and 4 is an event.
