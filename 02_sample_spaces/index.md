---
layout: lecture
title: Sample spaces
lecture: 2
date: Friday, February 5, 1999
transcriber: Bilge Demirköz
---

A sample space is a set $\Omega$ whose points are called sample
points, together with a family $\varepsilon$ of subsets, called events:

1. $\phi \in \varepsilon$
2. If $A \in \varepsilon$ then $A^c = \Omega - A \in \varepsilon$
3. If $A \in \varepsilon$ then $A \cap B \in \varepsilon$
4. If $A_1 A_2 \ldots \in \varepsilon$ disjoint, then $A_1 \cup A_2
\cup \ldots \in \varepsilon$. This results in countable additivity.

Given a sample space $\Omega$ with events $\varepsilon$, a probability
is a function $P: \varepsilon \rightarrow [0,1]$ such that

1. $P(\emptyset)=0$
2. $P(A^c) = 1- P(A)$
3. If $A_1 A_2 \ldots$ is a finite or an infinite sequence of
disjoint events, then $P(A_1 \cup A_2 \cup A_3 \cup \ldots) = P(A_1) +
P(A_2) + P(A_3) + \ldots$. This is the property called countable
additivity.

Two events in a sample space $\Omega$ with the probability $P$ are
independent when $P(A \cap B) =P(A) P(B)$. Three events $A$, $B$, $C$ are
independent when any two of them are independent and in addition $P(A
\cap B \cap C)=P(A) P(B) P(C)$.

Examples
--------

**1\.** $\Omega =$ finite set and $\varepsilon =$ all subsets of $\Omega$.
Choose a number $P(w)$ between 0 and 1, then for every sample point $w$
and set $$P(A) = \sum_{w\in A} P(w)$$ assuming $\sum_{w\in\Omega}
P(w)=1$.

**2\.** The Bernoulli Process

$$
\begin{eqnarray*}
\Omega &=& \text{all infinite sequences of 0's and 1's.}\\
w &=& (1, 0, 0, 1, 0, 1, 1, 0, \ldots)\\
\mbox{events: } H_n &=& \mbox{event that the } n^{th} \mbox{ toss is
1.}\\
H_n^c &=&\mbox{event that the } n^{th} \mbox{ toss is 0.}\\
\mbox{plus}&\mbox{any}& \mbox{ event obtained from } H_1, H_2, \ldots \mbox{ by the
rules } (1)(2)(3)(4) \mbox{ defining } \varepsilon.
\end{eqnarray*}
$$

Given a bias $p$ and letting $q=1-p$:

$$
\begin{eqnarray*}
P(H_n)&=&p \mbox{  then  } P(H_n^c)=q\\
P(H_k \cap H_n) &=& P(H_k)P(H_n)= p^2\\
P(H_i \cap H_j \cap \ldots \cap H_n)&=& P(H_i)
P(H_j) \ldots P(H_n)
\end{eqnarray*}
$$

_Remark 1:_ If $A$ and $B$ are independent events then $A$ and
$B^c$ are also independent.

_Remark 2:_ If $B \subseteq A$ then $P(A-B) =P(A)-P(B)$.\\
First, proof of Remark 2:

$$
\begin{eqnarray*}
A-B=A \cap B^c \Rightarrow P(A \cap B^c) &=& P(A) -P(B)\\
\mbox{so } P(A)&=&P(A \cap B^c) + P(B)\\
\mbox{then } A&=& (A \cap B^c) \cup B \Rightarrow \mbox{disjoint}
\end{eqnarray*}
$$

Now, the proof of Remark 1:

$$
\begin{eqnarray*}
P(A\cap B^c)&=& P(A) P(B^c) = P(A)(1-P(B)) = P(A)-P(A)P(B)\\
&=&P(A)-P(A\cap B) = P(A-A\cap B) =P(A\cap B^c)
\end{eqnarray*}
$$

Also consider the following:

If $H_k$ and $H_n^c$ are independent then $P(H_k \cap H_k^c)=pq$.

**Theorem:** These properties and remarks well-defines a probability on
all events.

**3\.** Another example of the Bernoulli Process

$$
\begin{eqnarray*}
A&=& \mbox{event that 1 never occurs.}\\
A&=& H_1^c \cap H_2^c \cap H_3^c \cap \ldots = \{ (0, 0, 0,\ldots)\}\\
\mbox{If } A&\subseteq& H_1^c \mbox{ then  } P(A) \leq P(H_1^c)=q\\
\mbox{If } A&\subseteq& H_1^c \cap H_2^c \mbox{ then  } P(A) \leq P(H_1^c
\cap H_2^c)=q^2\\
\mbox{If } A&\subseteq& H_1^c \cap H_2^c \cap H_3^c \cap \ldots
\mbox{ then } P(A) \leq q^n \mbox{ for all $n$ hence  } P(A) =0\\
\end{eqnarray*}
$$

*Remark*: If $A \subseteq B$ then $P(A)\leq P(B)$. Why?\\
Since $B= A \cup (B\cap A^c)$ so $P(B) = P(A) + P(B \cap A^c)$ hence
$P(A)\leq P(B)$.

**4\.** A run.

A run is a series of 1's or 0's repeated in the Bernoulli process.
Let B be event that the first run 11 occurs before the first 00 run.

$$
\begin{eqnarray*}
B &=& (H_1 \cap H_2) \cup (H_1 \cap H_2^c \cap H_3 \cap H_4) \cup 
(H_1 \cap H_2^c \cap H_3 \cap H_4^c \cap H_5 \cap H_6^c) \cup \ldots \\
& &\cup (H_1^c \cap H_2 \cap H_3) \cup 
(H_1^c \cap H_2 \cap H_3^c \cap H_4 \cap H_5) \cup \ldots \\
P(B) &=& p^2 + p^3 q + p^4 q^2 + p^5 q^3 + \ldots \\
& & + p^2 q + p^3 q^2 + p^4 q^3+ \ldots \\
&=& p^2(1+pq+p^2 q^2+\ldots) + p^2 q (1+ pq+ p^2 q^2 + \ldots)\\
&=& \frac{p^2}{1-pq} + \frac{p^2}{1-pq}\\ 
&=& \frac{p^2 + p^2 q}{1-pq}\\
\end{eqnarray*}
$$

Note that if $p=q=1/2$ then $P(B)= \frac{3/8}{3/4} = 1/2$.

