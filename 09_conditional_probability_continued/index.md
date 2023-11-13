---
layout: lecture
title: Conditional probability (continued)
lecture: 9
date: Wednesday, February 24, 1999
transcriber: Bilge Demirköz
---

### Understanding Conditional Probability - A Deeper Dive

Last time, we defined the conditional probability of an event given that another event happens:

$$
P(A|B)= \frac {P(A \cap B)} {P(B)}
$$

As we observed last time, this is sometimes written as $P_{B}(A)$, where A is the variable event: as A varies, its probability is defined on a fixed sample space (B). Of course, strictly speaking, every probability is conditional, but let's not get too philosophical just yet.

#### I. Law of Alternatives:
When we talk about a partition of the sample space into "blocks" of probabilities, we're essentially dealing with a union of disjoint blocks that covers $\Omega$. For instance, given an integer random variable $X$, we have:

$$
P(A)= \sum_{n} P(A|X=n)\cdot P(X=n)
$$

It's possible that $P(X=n)=0$ for some $n$. But the events $(X=n)$ for which $P(X=n)>0$ form a partition of $\Omega$. 

#### II. Law of Successive Probabilities (continued):
As we began discussing last time,

$$
\begin{aligned}
P(A \cap B) &= P(A)\cdot P(B|A) = P(A) \cdot \frac{P(A \cap B)}{P(A)}\\ 
P(B_1\cap B_2 \cap B_3) &= P(B_1) \cdot P(B_2|B_1) \cdot P(B_3|B_1 \cap B_2)\\ 
&= P(B_1) \cdot \frac{P(B_1 \cap B_2)}{P(B_1)} \cdot \frac{P(B_1 \cap B_2 \cap B_3)}{P(B_1 \cap B_2)}\\ 
P(B_1 \cap B_2 \cap \ldots \cap B_n) &= P(B_1) \cdot P(B_2|B_1) \cdot P(B_3|B_1 \cap B_2) \ldots P(B_n | B_1 \cap B_2 \cap \ldots \cap B_{n-1})
\end{aligned}
$$

The verification of this law is immediate, as we have previously sketched. Note that there exists a third law of some importance, but these are our "bread-and-butter" laws.

#### Examples: Sampling without Replacement
Consider an urn with $r$ red balls and $b$ black balls. We have a sequence of extractions $X_1$, $X_2$,\ldots,$X_{r+b}$. Previously, we discussed this rather informally. Now let's do it rigorously, using conditional probability:

$$
\begin{aligned}
P(X_1=1) &= \frac{r}{r+b}\\
P(X_1=0) &= \frac{b}{r+b}\\
P((X_1=1) \cap (X_2=0)) &= P(X_1=1) \cdot P(X_2=0|X_1=1)\\
P(X_2=0|X_1=1) &= \frac{b}{r+b-1}\\
P((X_1=1) \cap (X_2=0)) &= \frac{r\cdot b}{(r+b)(r+b-1)}
\end{aligned}
$$

{\it Conclusion:} The way we define probability on sample space without replacement is done in terms of conditional probability.

Let's generalize this result. More generally, 

$$
P((X_{1}=i_{1}) \cap (X_{2}=i_{2}) \cap \ldots \cap (X_{n}=i_{n})) = ?
$$

Notice how the numerator decreases by one depending on whether it's red or black. How do we express this? This probability is computed by the law of successive conditioning. It depends only on how many $i_1$, $i_2$,\ldots,$i_n$'s equal $1$. 

Let's say $i$ of them equals $1$ and $j$ of them equals $0$.

$$
\begin{aligned}
P((X_1=i_1) \cap (X_2=i_2) \cap \ldots \cap (X_n=i_n)) &= 
\frac{r(r-1)\ldots(r-i+1)b(b-1)\ldots(b-j+1)}{(r+b)(r+b-1)\ldots(r+b-i

-j+1)}\\
&= \frac{(r)_j (b)_j}{(r+b)_(i+j)}
\end{aligned}
$$

(by preceding reasoning, we don't know when the number of red/black balls clicks down by one, but multiplication is commutative, so we don't care!)

Before we philosophize on this result, let's compute something else.

What we have just computed is the probability of a sequence of $i$ 1's and $j$ 0's. It is not the probability of $i$ blacks and $j$ reds. Now, let's compute the other probability. Let $i+j=n$. Let A be the event that after extracting $n$ balls, we have $i$ red balls and $j$ black balls. There are ${ {r+b}\choose {n}}$ ways of extracting the balls. So, we get:

$$
\begin{aligned}
P(x=i) &= \frac{ { {r}\choose{i}} { {b}\choose{j}}}{ { {r+b}\choose{n}}} = \frac{ { {r}\choose{i}} { {b}\choose{n-i}}}{ { {r+b}\choose{n}}}\\
&= \frac{\frac{(r)_i}{i!} \frac{(b)_j}{j!}}{\frac{(r+b)_n}{n!}} = \frac{n!}{i! j!} \frac{(r)_i (b)_j}{(r+b)_{i+j}}\\
&= { {n}\choose{j}} \frac{(r)_i (b)_j}{(r+b)_{i+j}}
\end{aligned}
$$

This is called the *Hyper-geometric distribution*.

But this is simply the ways of distributing $n$ balls in $i$ places. We didn't have to do it indirectly.

Now let's solve another problem. We have an urn with $n$ number of colors, and so the sequence of extractions is $X_1$, $X_2$,\ldots, $X_{c_1+c_2+\ldots+c_n-1}$. Then,

$$
\begin{aligned}
P((X_1=i) \cap (X_2=j)) &= P(X_1=i) \cdot P(X_2=j|X_1=i)\\ 
\text{if } i \neq j \text{ then} &= \frac{c_i}{c_1+c_2+\ldots+c_n} \cdot \frac{c_j}{c_1+c_2+\ldots+c_n-1}\\
\text{if } i = j \text{ then} &= \frac{c_i}{c_1+c_2+\ldots+c_n} \cdot \frac{c_i-1}{c_1+c_2+\ldots+c_n-1}\\ 
\end{aligned}
$$

Let's solve for the general case, $P((X_1=i_1) \cap (X_2=i_2) \cap \ldots \cap (X_k=i_k))$. If among $i_1$, $i_2$,\ldots, $i_k$ there are $j_1$ equal to 1, $j_2$ equal to 2, and $j_n$ equal to $n$, then,

$$
P((X_1=i_1) \cap (X_2=i_2) \cap \ldots \cap (X_k=i_k)) = \frac{(c_1)_{j_1} (c_2)_{j_2} \ldots (c_n)_{j_n}}{(c_1+c_2+\ldots+c_n)_{k}}
$$

In a sample space of $k$ marbles, the probability of finding $j_1$ balls marked 1, $j_2$ balls marked 2, and $j_n$ balls marked $n$, where $j_1+j_2+\ldots+j_n$ is equal to $k$, is given by:

$$
\begin{aligned}
\frac{ { {c_1}\choose{j_1}} { {c_2}\choose{j_2}} \ldots { {c_n}\choose{j_n}}}{ { {c_1+c_2+\ldots+c_n}\choose{k}}} &= { {k}\choose{j_1, j_2,\ldots,j_n}} \frac{(c_1)_{j_1} (c_2)_{j_2} \ldots (c_n)_{j_n}}{(c_1+c_2+\ldots+c_n)_{k}}\\
P(X_2=j) &= \sum_{i} P(X_2=j|X_1=i) \cdot P(X_1=i)\\
\text{but } P(X_2=j|X_1=i) &= (\frac{c_i-1}{c_1+c_2+\ldots+c_n-1}) + (\sum_{j \neq i} \frac{c_j}{c_1+c_2+\ldots+c_n-1})\\


\text{and }P(X_1=i) &= \frac{c_i}{c_1+c_2+\ldots+c_n}\\
\end{aligned}
$$

After a lot of algebra – and if you don't believe me, you can calculate it for yourselves – we have:

$$
P(X_2=j)= \frac{c_{j}}{c_1+c_2+\ldots+c_n}
$$

But there is an easier way to do this. 

$$
\begin{aligned}
P(X_2=i) &= P(X_1=i)\\
P((X_5=j) \cap (X_2=i)) &= P((X_1=j) \cap (X_2=i))
\end{aligned}
$$

This is a very important fact, as we mentioned before. We can compute all joint distributions very easily because they are symmetric.

**Definition:**

A sequence of $X_1, X_2,\ldots$ of integer random variables is **exchangeable** when all $P((X_i) \cap \ldots \cap (X_k=i))$ depend only on how many $i_1, i_2,\ldots$, $i_n$ equal $\ldots, -1, 0, 1, 2, \ldots$.

For example, in Maxwell-Boltzmann Statistics, $\Theta_1, \Theta_2,\ldots, \Theta_n$ are exchangeable.

If you have an infinite sequence of events, it is exchangeable if any subset is exchangeable.

A sequence $X_1, X_2,\ldots$ of independent identically distributed random variables is "a fortiori" also exchangeable.
