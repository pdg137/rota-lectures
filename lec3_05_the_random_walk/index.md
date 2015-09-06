---
layout: lecture
title: The Random Walk
---

Today we will review the random walk.  Since this is one of the most
intensively studied stochastic processes, it's worthwhile to do it
over again, from scratch.

A _random walk_ is a sequence $Y_1, Y_2, \ldots$ of independent,
identically distributed random variables, where
$P(Y_n=+1) = {1\over 2}$, and $P(Y_n=-1) = {1\over 2}$.
We define, in addition, _the position at time $n$_:
$$G_n = \sum_{i=1}^n Y_i$$
We draw a sample point of the random walk by graphing $G_n$ with
respect to time, and connecting the dots.  The simplest thing to
compute is the probability distribution of $G_n$,

$$P(G_n=x) = {1\over 2^n} \left( n \atop {n+x \over 2} \right).$$

We now make up a new random variable, $Z_a$, as follows.  The event
that $Z_a=n$ is defined to be
$(G_1<a)\cap(G_2<a)\cap\cdots\cap(G_{n-1}<a)\cap(G_n=a).$  This is
the time it takes, or ``the waiting time,'' to reach level $a$.

Also, we define $M_n$ to be the maximum of $G_0,G_1,\ldots,G_n$, the
maximum level reached in the first $n$ steps.  We want their
probability distributions --- that's no joke.  To warm up, notice
that

$$(M_n=a) = (Z_a\le n)-(Z_{a+1}\le n).$$

That is, if the maximum
after $n$ steps is $a$, you've reached level $a$ already but not level
$a+1$.  Unfortunately, this observation won't be of much use to us.
However, the following one is essential.

The reflection principle
------------------------

Consider the event $(G_n=x)\cap(Z_a\le n)$, for $x\le a$.  Our path
has crossed level $a$ at some point, and is now at a height $x$, below
$a$.  Find the point where the graph first reaches level $a$, and
reflect the prior portion about the line $G=a$.  The origin is always
mapped up to a height $2a$, so every such graph can be transformed
into a unique graph that _starts_ at $2a$ and drops after $n$
steps to a
height $x$.  Since all of graphs that do that must cross $a$ at some
intermediate time, we have a one-to-one correspondence between the two
types of graphs.  Thus, the probability of reaching $a$ but coming
back down to $x$ is the same as the probability of starting at the
origin and dropping to a height of $2a-x$.  This is called _the
reflection principle_.

$$P((G_n=x)\cap(Z_a\le n)) = P(G_n=2a-x) = P(G_n=x-2a).$$

This is a good way to simplify some problems --- don't forget it!

Using the reflection principle we can compute the distribution of $Z_a$:

$$P(Z_a=n)=P(Z_a=n \vert Y_n=1)P(Y_n=1)+P(Z_a=n \vert Y_n=-1)P(Y_n=-1).$$

Since last step must be up for the path to reach a new maximum,

$$P(Z_a=n \vert Y_n=-1)=0$$

and we have:

$$
\begin{eqnarray*}
P(Z_a=n)&=&{1\over2}P(Z_a=n \vert Y_n=1) \\
        &=&{1\over2}\left\{ P(G_{n-1}=a-1) - P((G_{n-1}=a-1)\cap(Z_a \le n-1))\right\}
\end{eqnarray*}
$$

This is ready for the reflection principle; it becomes

$$
\begin{eqnarray*}
{1\over2}\left\{ P(G_{n-1}=a-1) - P(G_{n-1}=2a-(a-1))\right\} = {1\over2}\left\{ P(G_{n-1}=a-1) - P(G_{n-1}=a+1)\right\}
\end{eqnarray*}
$$

We finally have

$$P(Z_a=n)
	 = {1\over2^n}\left[ \left( n-1 \atop {n+a\over2}-1 \right)
			   + \left( n-1 \atop {n+a\over2} \right) \right]
	 = {a \over 2^n\cdot n} \left( n \atop {n+a\over 2} \right).$$

Next, let's roll up our sleeves and compute the probability
distribution of the maximum $M_n$.

$$
\begin{eqnarray*}
P((M_n=a)\cap(G_n=x)) &=& P((M_n\ge a)   \cap(G_n=x))\\
                      & &- P((M_n \ge a+1)\cap(G_n=x))\\
                      &=&P((Z_a \le n)\cap(G_n=x))\\
                      & &- P((Z_{a+1} \le n)\cap(G_n=x))\\
                      &=&P(G_n=x-2a) - P(G_n=x-2a-2).
\end{eqnarray*}
$$

Did this get us any further?  Sure:

$$P(M_n=a) = \sum_{x\le a} P((M_n=a)\cap(G_n=x)) = P(G_n=a)+P(G_n=a+1).$$

A wonderful cancellation has occurred!

Conclusion
----------

This is only the beginning of the vast and beautiful theory of the
random walk.  Here are two more examples of the kinds of things one
can compute.  First, if a random walk is zero at step $2n$, we might
be interested in the event $A_{2k}$ that exactly $2k$ sides are above
the t-axis.  It turns out that this probability is the same for all
$k$'s!
Lastly, we might want to know the number of times the random walk
has changed sign after $n$ steps.  We define $p_0$ to be the
probability that it never does, $p_1$ to be the probability that it
changes sign once, and so on.  This is quite difficult to compute,
but, amazingly enough, we would find that $p_0>p_1>p_2>\cdots$.
