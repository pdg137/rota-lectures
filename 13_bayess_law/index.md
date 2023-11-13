---
layout: lecture
title: Bayes's Law
lecture: 13
date: Monday, March 8, 1999
transcriber: Winston Chang and Daniel Riordan
---

### Preliminary Discussion: Combinatorial Identity

$$
\sum_{j=0}^{n} {j \choose i}{n-j \choose k-i} = {n+1 \choose k+1}
$$

#### Example
- For $i=0$: $\sum_{j} {n-j \choose k} = {n+1 \choose k+1}$
- For $i=1$: $\sum_{j} j {n-j \choose k-1} = {n+1 \choose k+1}$
- etc.

To derive Bayes's Law, we define a new sample space.

#### New Sample Space: $\Omega_{FD}$ = Fermi-Dirac statistics
- Sample points $\omega$ are all subsets with exactly $k+1$ elements.
- The probability of each sample point $\omega$ is given by: $P(\omega) = \frac{1}{ {n+1 \choose k+1}}$
- The probability of an event $A$ is given by: $P(A) = \sum_{\omega \epsilon A} P(\omega)$

#### Random Variable $C_{i+1}$ on $\Omega_{FD}$
- $C_{i+1}$ = (i+1)-th element in a sample point $C_{i+1}(\omega)$
- Probability distribution: 
  - $P(C_{i+1} = j+1) = \frac{ {j \choose i}{n-j \choose k-i}}{ {n+1 \choose k+1}}$
  - $\sum_{j} P(C_{i+1} = j+1) = 1$
  - Therefore, $\sum_{j} \frac{ {j \choose i}{n-j \choose k-i}}{ {n+1 \choose k+1}} = 1$

By multiplying both sides by ${n+1 \choose k+1}$, we get the Combinatorial Identity:

$$
\sum_{j=0}^{n} {j \choose i}{n-j \choose k-i} = {n+1 \choose k+1}
$$

#### Law of Alternatives

$$
P(A) = \sum_{w \epsilon A} P(A|B)P(B)
$$

$$
P(A|B) = \frac{P(A \cap B)}{P(B)}
$$

#### Bayes's Law

$$
P(B|A) = \frac{P(B \cap A)}{P(A)} = \frac{P(A|B)P(B)}{P(A)} = \frac{P(A|B)P(B)}{\sum_{B \epsilon \Pi} P(A|B)P(B)}
$$

#### Terminology
- $P(B)$ is called the "Prior."
- $P(B\|A)$ is called the "Posterior."
- $P(A\|B)$ is called the "Likelihood."

#### Scientific Induction Example
Consider an urn with n balls, some red and some black. The number of balls n, is known, while the number of red and black balls are not known. Let $U$ = the number of red balls in the urn. A sample of $k$ balls is taken out of the urn without replacement. Let $A$ = the number of reds in the sample of $k$ balls. Then,

$$
P(A=i|U=j) = \frac{ {j \choose i}{n-j \choose k-i}}{ {n \choose k}}
$$

This is the hypergeometric distribution. We want to find $P(U=j\|A=i)$.

$$
P(U=j|A=i) = \frac{P(A=i|U=j)P(U=j)}{P(A=i)}
$$

For this,
- $P(U=j\|A=i)$ is the posterior.
- $P(A=i\|U=j)$ is the likelihood.
- $P(U=j)$ is the prior.

#### Case 1: Uniform Prior
Assuming a uniform prior, we find:

$$
P(U=j|A=j) = \frac{ {j \choose i}{n-j \choose k-i}}{ {n \choose k}} \cdot \frac{\frac{1}{n+1}}{\sum_{j} \frac{ {j \choose i}{n-j \choose k-i}}{ {n \choose k}} \cdot \frac{1}{n+1}} = \frac{ {j \choose i}{n-j \choose k-i}}{ {n+1 \choose k+1}}
$$

#### Case 2: Conjugate Prior
Suppose the balls in the urn are initially uncolored, and the devil independently colors each ball red with probability

 $p$ and black with probability $q$. Let $X_i$ represent the $i^{th}$ ball.

The total number of red balls equals $X_1 + X_2 + \ldots + X_n = S_n$.

$$
\begin{aligned}
P(A=i|U=j) &= \frac{ {j \choose i}{n-j \choose k-i}}{ {n \choose k}} \\
P(U=j) &= { {n \choose j}}p^{j}q^{n-j} \\
P(A=i) &= { {k \choose i}}p^{i}q^{k-i} \\
P(U=j|A=i) &= \frac{P(A=i|U=j)P(U=j)}{P(A=i)} \\
&= { {n-k \choose j-i}}p^{j-i}q^{n-j-k+i}
\end{aligned}
$$

This simple result suggests that the extensive calculations we just performed were probably unnecessary.
