---
layout: lecture
title: Random variables
lecture: 4
date: Friday, February 12, 1999
transcriber: Pegah Ebrahimi
---

$X(\omega)$ is an integer. From the standpoint of random variables' occupancy, an integer is assigned to every block. A **Partition** of a sample space, say $\Pi$, is a countable family of events such that:

1. If $B \in \Pi$, then $P(B) > 0$.
2. If $B_{1}, B_{2} \in \Pi$, then $B_{1} \cap B_{2} = \emptyset$ if $B_{1} \neq B_{2}$.
3. $P\left(\bigcup B\right) = 1$ for $B \in \Pi$.

This does not imply that the union of all Bs is the sample space. In a **random variable**, the family $\{(X = n)... n\ \text{integers}\}$ for which $P(X = n) > 0$, forms a partition of the sample space $\Omega$. If **X** is an integer random variable, then the sequence $p_n=P(X=n)$ is called the probability distribution of X. So we have:

$$ p_n > 0 \quad \text{and} \quad \sum_n p_n =1 $$

since 

$$ \sum_n p_n = \sum_n P(X = n) $$

The events are disjoint so by countable additivity, we have

$$ = P\left(\bigcup_n(X = n)\right) = P(\Omega) = 1 $$

**Expectation:** (average value of the Random Variable)

$$ E(X) = \sum_n n P(X = n) = \sum_n n p_n $$

Given two random variables on $\Omega$, say X and Y, with $P(X = n) = p_n$ and $P(Y = n) = q_n$ where $p_n + q_n \neq 1$. Let the joint distribution of X and Y, $P((X = i) \cap (Y = j))$, be the double-index sequence $r_{ij}$.

X and Y are independent when $P((X = i) \cap (Y = j)) = P(X = i) \cdot P(Y = j)$ for all integers *i* and *j*, and so $r_{ij} = p_i q_j$. Now consider:

$$ (X = i) \cap \Omega = (X = i) \cap \left(\bigcup_j (Y = j)\right) = \bigcup_j (X = i) \cap (Y = j) $$
$$ P(X = i) = \sum P((X = i) \cap (Y = j)) $$
$$ p_i = \sum_i^j r_{ij} \quad\quad q_j = \sum_i^j r_{ij} $$

**Applications:**

What is the probability distribution of the random variable X + Y?

$$ (X + Y = n) = \bigcup_i (X = i) \cap (Y = n - i) $$

Taking Probabilities:

$$ P(X + Y = n) = \sum_i P((X = i) \cap (Y = n - i)) = \sum_i r_{i, n - i} $$

In particular, if X and Y are independent:

$$ P(X + Y = n) = \sum_i p_i q_{n - i} $$

**Theorem**: "The Gift of God Theorem"

$$ E(X + Y) = E(X) + E(Y) $$

Proof:

$$ E(X + Y) = \sum_n n P(X + Y = n) = \sum_n n \sum_i P((X = i) \cap (Y = n - i)) $$
$$ = \sum_{i,n}(i + (n - i)) P((X = i) \cap (Y = n - i)) = \sum_{i,j}(i + j) P((X = i) \cap (Y = j)) $$
$$ = \sum_{i,j} i P((X = i) \cap (Y = j)) + \sum_{i,j} j P((X = i) \cap (Y = j)) $$
$$ = \sum_i i \sum_j P((X = i) \cap (Y = j)) + \sum_j j \sum_i P((X = i) \cap (Y = j)) $$

by countable additivity

$$ = \sum_i i P\left(\bigcup_j (X = i) \cap (Y = j)\right) + \sum_j j \sum_i P((X = i) \cap (Y = j)) $$

by distributive law

$$ = \sum_i i P((X = i) \cap \bigcup_j (Y = j)) + \sum_j j \sum_i P((X = i) \cap (Y = j)) $$

and since $\Omega = \bigcup_j (Y = j)$

$$ = \sum_i i P((X = i) \cap \Omega) + \sum_j j P(Y = j) $$

But note that $E(X) = \sum_i i P(X = i)$ and similarly for E(Y). So we have

$$ E(X + Y) = E(X) + E(Y) $$
