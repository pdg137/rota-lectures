---
layout: lecture
title: Conditional probability (continued)
lecture: 10
date: Friday, February 26, 1999
transcriber: Daniel Vlasic and Pegah Ebrahimi
---

### Exchangable Random Variables (continued)

#### Review
Say we have three random variables $X_1, X_2, X_3$; they are exchangeable when:

$$
\begin{aligned}
P((X_1=i) \cap (X_2=j) \cap (X_3=k)) &= P((X_1=k) \cap (X_2=j) \cap (X_3=i)) \\
 &= \text{any other permutation}\\
P(X_1=i) &= \sum_{j,k} P((X_1=i) \cap (X_2=j) \cap (X_3=k)) 
\end{aligned}
$$

Why? Because:

$$
\begin{aligned}
(X_1=i) &= (X_1=i) \cap \Omega \qquad (\ast)\\
\Omega &= \bigcup_j (X_2=j) = \bigcup_k (X_3=k) \\
\Omega &= \bigcup_j (X_2=j) \cap \bigcup_k (X_3=k) \\
\Omega &= \bigcup_{j,k} (X_2=j) \cap(X_3=k)
\end{aligned}
$$

Substituted in ($\ast$) we obtain:

$$
\begin{aligned}
(X_1=i) &= (X_1=i) \cap \bigcup_{j,k} (X_2=j) \cap (X_3=k) \\
&= \bigcup_{j,k} (X_1=i) \cap (X_2=j) \cap (X_3=k) \\
P(X_2=i) &= \sum_{j,k} P((X_1=j) \cap (X_2=i) \cap (X_3=k)) = P(X_1=i) 
\end{aligned}
$$

Thus, exchangeable random variables are *i.d.*

### The Polya Urn Process
- There is an urn with $r$ red balls and $b$ black balls.
- Extract a ball, replace $c+1$ balls of the color extracted; repeat.

$$
X = \left\{
\begin{array}{ll}
      1    & \text{if the } n^{th} \text{ ball is red} \\
      0    & \text{if the } n^{th} \text{ ball is black}
\end{array}
\right. 
$$

$$
\begin{aligned}
P(X_1=1) &= \frac{r}{r+b} \\
P(X_1=0) &= \frac{b}{r+b} \\
P((X_1=1) \cap (X_2=0)) &= P(X_1=1)P(X_2=0|X_1=1) \\
                        &= \frac{r}{r+b} \cdot \frac{b}{r+b+c} \\
P((X_1=1) \cap (X_2=1)) &= \frac{r}{r+b} \cdot \frac{r+c}{r+b+c}
\end{aligned}
$$

Generalizing this result for any sequence of extractions:

$$
\begin{aligned}
P((X_1=i_1) \cap (X_2=i_2) \cap \ldots \cap (X_n=i_n)) &= \frac{r(r+c)(r+2c) \ldots (r+ (i-1)c) \cdot b(b+c)(b+2c) \ldots (b+(j-1)c)}{(r+b)(r+b+c)(r+b+2c) \ldots (r+b+(n-1)c)}
\end{aligned}
$$

where there are $i$ reds, $j$ blacks, and $i+j=n$. Therefore, the $n$ random variables $X_i$ are exchangeable.

- $c= 0$ means "sampling with replacement"
- $c=-1$ means "sampling without replacement"

$$
P(X_2=1) = \underbrace{P(X_2=1|X_1=0)P(X_1=0) + P(X_2=1|X_1=1)P(X_1=1)}_{\text{DON'T HAVE TO DO THAT}} = \frac{r}{r+b}
$$

#### Another Process:
- There are $r$ red balls and $b$ black balls in an urn.
- If red is picked, replace with $c_r+1$ reds.
- If black, replace with $c_b+1$ blacks.

$$
\begin{aligned}
P(X

_1=1) &= \frac{r}{r+b} \\
P(X_1=0) &= \frac{b}{r+b} \\
P((X_1=1) \cap (X_2=0)) &= P(X_1=1)P(X_2=0|X_1=1) = \frac{r}{r+b} \cdot \frac{b}{r+b+c_r} \\
P((X_1=0) \cap (X_2=1)) &= \frac{b}{r+b} \cdot \frac{r}{r+b+c_b} 
\end{aligned}
$$

### Example: Bernoulli Process
A=event that the first run of $h$ heads occurs before the first run of $t$ tails.  
Warm-up: $P(A|(X_1=1) \cap (X_2=0))$

The sample space consists of all sample points:

$$
(1, 0, w_3, w_4, w_5 \ldots)
$$

$$
P(A|(X_1=1) \cap (X_2=0)) = P(A|X_1=0)
$$

similarly,

$$
\begin{aligned}
P(A|(X_1=1) \cap (X_2=1) \cap \ldots \cap (X_i=1) \cap (X_{i+1}=0)) &= ? \\
w = (111...10w_{i+2}w_{i+3}...) &= P(A|X_1=0) \text{ if } i < h\\
&= 1 \text{ if } i \geq h
\end{aligned}
$$

similarly,

$$
P(A|(X_1=0) \cap (X_2=0) \cap \ldots \cap (X_i=0) \cap (X_{i+1}=1)) = \,?
$$

Sample space consists of all points:

$$
\underbrace{000\ldots0}_i1\omega_{i+2}\omega_{i+3}\ldots
$$

$$
P(A|X_1)P(X_1=1)+P(A|X_1=0)P(X_1=0)=\underbrace{P(A|X_1=1)}_?p+\underbrace{P(A|X_1=0)q}_?
$$

$$
P(A|X_1=1)=P_{(X_1=1)}(A)
$$

Let $W_0$ be the waiting time for the first tail,  

$$
P_{(X_1=1)}(W_0>i) = p^{i-1}
$$

$$
P_{(X_1=1)}(W_0 \leq i) = 1-P_{(X_1=1)}(W_0>i) = 1-p^{i-1}
$$

We will finish this next time.
