---
layout: lecture
title: Random variables (continued)
lecture: 7
date: Wednesday, February 17, 1999
transcriber: Vladislav Gabovich
---

Let us continue with the topic of random variables, which is relevant
to our study of the Bernoulli process.
We saw in previous lectures that in the Bernoulli process, we have
several notable random variables.
For example, let us define

$$
X_{n} = \text{ the outcome of the n-th toss.}
$$

Also,

$$
\begin{aligned}
P(X_{n}=1) &= p  \\
P(X_{n}=0) &= q=1-p
\end{aligned}
$$

The random variables in the sequence $X_{1},X_{2},X_{3},\ldots$ are
independent, that is, every finite subset of them is independent.
(An elegant way to define the Bernoulli process is through a
sequence of random variables).
In real life, sample spaces are more often defined by random variables
and their distributions, than by sample points, events and their
probability. In quantum probability, for example, one is forced to
study random variables, since there is no "point" space to look at. 

(cont'd) **The Bernoulli Process**

Consider the sequence

$$
T_{1},T_{2},T_{3}, \ldots
$$

where $T_{i}$ denotes the gap, in tosses, between successive "heads".
Last time, we argued convincingly that these random variables are
independent, and that their probability distributions are given by

$$
P(T_{1}=n)=q^{n-1}p
$$

Then we considered the random variable

$$
S_{n}= X_{1}+X_{2}+X_{3}+\ldots+X_{n},
$$

the number of successes (heads) in the first n tosses.
This random variable is given by

$$
P(S_{n}=k)= \binom{n}{k} \cdot p^{k}q^{n-k}
$$

This is our "bread-and-butter" probability - don't ever forget it!

Let's talk about expectations now.
What is the expectation of $X_{n}$, $E(X_{n})$ ?
By definition, the scriptures say, it is:

$$
E(X_{n}) = \sum_{j} j \cdot P(X_{n}=j)
$$

Since $X_{n}$ takes only the values $\{0,1\}$, this sum reduces to
the first two terms:

$$
E(X_{n}) = 0 \cdot P(X_{n}=0) + 1 \cdot P(X_{n}=1) = p
$$

Next, let's compute $S_{n}$. The scriptures say that this must
be computed in terms of the probability distribution,

$$
\begin{aligned}
E(S_{n}) &= \sum_{k=0}^{n}k\cdot P(S_{n}=k) \\
&= \sum_{k=0}^{n}k \binom{n}{k} \cdot p^{k}q^{n-k} = \text{mess}
\end{aligned}
$$

There must be a simpler way to do this. We would go into a 
calculation like the one above only if we were "backed to the wall".
We'll use the God-given theorem: observe, that

$$
E(S_{n}) = E(X_{1}) + E(X_{2}) + E(X_{3}) + \ldots + E(X_{n})
$$

But, $X_{1} \ldots X_{n}$ are identically distributed, and hence
have the same expectation,

$$
E(S_{n}) = n \cdot p
$$

And the horrendous sum is just that, $n \cdot p$ !
Now $E(T_{1})$ - there is a trick to do it in one step,
$ = \frac{1}{p}$ (Why?)
The bigger $p$ is, the shorter the wait.

Let's now consider

$$
W_{k} = \text{the waiting time for the k-th head,}
$$

another important random variable.
Clearly,

$$
W_{k} = T_{1}+T_{2}+T_{3}+ \ldots + T_{k}
$$

We could compute the distribution of $W_{k}$ the hard way,
using the fact that $T_{i}$s are independent, but instead,
notice that the event $P(W_{k})$ means

1. "1" at the n-th toss
2. Pick $k-1$ "1"s from first $n-k$ tosses

Therefore, we write

$$
P(W_{k}=n) = \binom{n-k}{k-1} p^{k} q^{n-k}
$$

This topic inspires some tough questions, ones of great
relevance in practice. For example, to test the randomness
of a sequence, we can try to check probabilities of different
patterns.

**The Borel-Cantelli lemma**

This lemma is best understood from examples.
Consider a pattern - a run of 17 consecutive heads ("1"s).
We ask the following question:
Suppose $p<1$. What is the probability that this run will
ever occur?

Let $B =$ the event that a run of 17 heads will occur.
We want to show that $P(B) =1$.
(Intuitively this is fine; but let us stop handwaving.
our proof will be rigorous, though cute).

Let us consider other events:

$$
\begin{aligned}
B_{1} &= \text{event that tosses 1-17 are "1"s} \\
B_{2} &= \text{event that tosses 18-34 are "1"s,}
\end{aligned}
$$

etc, a sequence $\{ B_{n} \}$. 
Of course, a run can occur anywhere, but our argument
will be made on the basis of these cases.
Observe, that $B_{1},B_{2}, \ldots$ are independent.
Since B is the event that a run of 17 "1"s \textbf{ever} occurs,

$$
B \supseteq B_{1} \cup B_{1} \cup B_{1} \cup \ldots
$$

which means

$$
B \subseteq B_{1}^{c} \cup B_{1}^{c} \cup B_{1}^{c} \cup \ldots
$$

Since $B_{i}$'s are independent, $B_{i}^{c}$'s are independent as well.
Hence, we obtain,

$$
\begin{aligned}
P(B^{c}) & \leq & P(B_{1}^{c} \cup B_{1}^{c} \cup \ldots \cup B_{k}^{c}) \quad \forall k \\
& = & P(B_{1}^{c})P(B_{2}^{c}) \ldots P(B_{k}^{c})
\end{aligned}
$$

Now,

$$
P(B_{i}^{c}) = 1-P(B_{i}) = 1-p^{17}
$$

Of course, $P(B_{2})=P(B_{1})$; therefore

$$
P(B^{c}) = 1-P(B) = (1-p^{17})^k
$$

As $k \rightarrow \infty$, $P(B^{c}) \rightarrow 0$,
hence

$$
P(B) = 1
$$

We have shown, beyond a reasonable doubt, that $P(\text{run of 17}) = 1$.

By the same reasoning, the Borel-Cantelli lemma applies to any 
pattern whatsoever, and we have

$$
P(\text{\bf any pattern}=1)
$$

Not quite. What we really proved is more - not only does a run 
(of 17 heads) sometimes occur, but it occurs \textbf{infinitely} 
many times. For, suppose the pattern stops occurring after some
finite step $N$. This immediately contradicts what we just proved!
Treating N as our starting step, since the pattern doesn't know
that it already occurred, it must occur again, for the "first time".
Applied to any finite step, and for any finite pattern, this argument 
implies that:

> **Every finite pattern occurs infinitely many times with probability 1.**

In other words, typing at random, a monkey will type the Bible 
infinitely many times!

Question: Why doesn't this argument apply to infinite patterns?

Answer:   Because if $l=\infty$, $P(B^{c}) \leq (1-p^{l})^{k} \neq 0$

Now we will proceed to fresh sample spaces and random variables,
sampling with and without replacement - "bread-and-butter"
probability.

**Sampling with Replacement**

Imagine a urn of balls, marked $1 \ldots n$, and let $c_{i}$ denote the
number of balls marked $i$ in the urn, $1 \leq i \leq n$.
We will extract a ball at random from the urn, examine it, and put it
back. We will define the sample space as 

$$
\Omega = \{ w = (w_{1},w_{2}, \ldots,w_{i},\ldots); 1 \leq i \leq n \}
$$

The probabilities in this example are obvious.

Let's define 

$$
X_{n} = \text{ the result of the n-th sample.}
$$

Then

$$
P(X_{i}=1) = \frac {c_{1}}{c_{1}+c_{2}+\ldots+c_{n}}
$$

The random variables $X_{1}, X_{2}, \ldots$ are independent. Events are the
values of random variables. The sample space of sampling with
replacement is very similar to coin tossing, that is, tossing of an n-sided
die, and therefore the questions are similar. 

We've been talking about a sequence of independent random variables 
which are identically distributed. In the next lecture, professor 
S.Billey will talk about random walks.

**Sampling without Replacement**

The process of picking out balls from the urn is the same, except
we throw out each ball we pick out, instead of putting it back into
the urn.

$$
\Omega = \{w = (w_{1},w_{2}, \ldots, w_{c_{1}+\ldots+c_{n}} \}
$$

Again, define,

$$
X_{n} = \text{result of the n-th extraction.}
$$

Clearly,

$$
P(X_{1}=i) = \frac {c_{i}} {c_{1}+\ldots+c_{n}}
$$

I claim,

$$
P(X_{n}=i) = \frac {c_{i}} {c_{1}+\ldots+c_{n}} = P(X_{1}=i) 
$$

*Proof by the Principle of Sufficient Reasoning:* Consider extracting
all the balls and permuting them in every possible way. Since the
balls do not have cognitive capabilities, the probability distribution
remains consistent, whether we are observing the 1st extraction or the
n-th extraction. This implies that while the extractions $X_{1},
X_{2}, \ldots$ are not independent (due to the removal of balls
altering subsequent probabilities), they are identically distributed
in terms of their initial probabilities.

How do we get a joint distribution of random variables?

Suppose we want to compute $P((X_{3}=i) \cap (X_{n}=j))$. Again, by
the principle of sufficient reasoning, we argue that since the balls 
do not think and the distributions are the same, we can freely permute
the indices:

$$
\begin{aligned}
P((X_{3}=i) \cap (X_{n}=j)) &= P((X_{1}=i) \cap (X_{2}=j)) \\
&= \left\{ \begin{array}{rcl}
\frac{c_{i}c_{j}}{(c_{1}+c_{2}+\ldots+c_{n})(c_{1}+c_{2}+\ldots+c_{n-1})}
& \text{if} & i \neq j\\
\frac{c_{i}(c_{i}-1)}{(c_{1}+c_{2}+\ldots+c_{n})(c_{1}+c_{2}+\ldots+c_{n-1})}
& \text{if} & i = j
\end{array} \right\}
\end{aligned}
$$

Question: How to express precisely the fact that it doesn't matter
which is which, that we can permute the extractions?
