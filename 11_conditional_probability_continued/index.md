---
layout: lecture
title: Conditional probability (continued)
lecture: 11
date: Wednesday, March 3, 1999
transcriber: Carla Pellicano
---

### Bernoulli Process

Let $A$ be the event that the first run of $h$ heads will occur before the first run of $t$ tails. By the *law of alternatives*:

$$
P(A) = P(A|X_1=1)\underbrace{P(X_1=1)}_{p} + P(A|X_1=0)\underbrace{P(X_1=0)}_{q}
$$

If we can compute these two conditional probabilities, $p$ and $q$, then we can compute the probability of $A$. 

$$
P((A|X_1=0) \cap (X_2=1)) = P(A|X_1=1)
$$

We want to compute this probability on all sample points. Given any sample space of zeros and ones, as long as all preceding runs have fewer than $t$ zeros, we can begin computing $P(A)$ with the last run of ones. Take, for example, the sample space: $(0, 1, \omega_3, \omega_4,...)$. If we let $t=5$ and $h=7$, then we can begin counting from $\omega_2$, the first one in our sample space.

$$
\begin{aligned}
P_{(X_1=1)}(A) &= P_{(X_1=1)}(A|W_o \leq h)P_{(X_1=1)}(W_o \leq h)+P_{(X_1=1)}(A|W_o > h)P_{(X_1=1)}(W_o > h)
\end{aligned}
$$

$W_o$ represents the waiting time for the first zero and events $(W_o \leq h)$ and $(W_o > h)$ partition $\Omega$. Once we get our first zero, we have to start counting over again.

$$
\begin{aligned}
P(A|X_1=0) P_{(X_1=1)}(W_o \leq h) + P_{(X_1=1)}(W_o > h) &= P(A|X_o=0)(1-p^{k-1}) + p^{h-1} \\
P(A|X_1=1) &= P(A|X_1=0)(1-p^{h-1}) + p^{h-1} \\
P_{(X_1=0)}(A) &= P_{(X_1=0)}(A|W_1 \leq t) P_{(X_1=0)}(W_1 \leq t) + P_{(X_1=0)}(A|W_1 > t) P_{(X_1=0)}(W_1 > t)
\end{aligned}
$$

Where $W_1$ is the waiting time for the first 1. $P_{(X_1=0)}(A\|W_1 > t)$ must equal zero, because we would have already lost! (having already gotten a run of $t$ tails).

$$
\begin{aligned}
P_{(X_1=0)}(W_1>t) &= q^{t-1} \\
P_{(X_1=0)}(W_1 \leq t) &= 1 - q^{t-1} \\
P_{X_1}(A) &= P(A|X_1=1)(1-q^{t-1})
\end{aligned}
$$

For our final answer, we get:

$$
P(A) = \frac{(p^{h-1})(1-q^t)}{p^{h-1}+q^{t-1}-p^{h-1}q^{t-1}}
$$

### Easy Example: Monty Hall Paradox
Imagine we have 100 boxes, one of which contains a marble. There are two players: one good guy (who doesn't know which box contains the ball) and one bad guy (who does). Step 1: the good guy chooses a box. Let $A$ be the event that the good guy chooses the box with the marble. We know that $P(A)=1/100$. Step 2: the bad guy opens 98 boxes, which contain no marbles. He then offers to trade his remaining box with the good guy. The good guy switches, since the probability that he has chosen correctly the first time was 1/100, while the chance of choosing correctly now is 1/2.
