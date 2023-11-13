---
layout: lecture
title: More examples of sample spaces...
date: Wednesday, February 10, 1999
transcriber: David Wang and Shivkumar Venkatasubrahmanyam
---

Example 4 : Maxwell-Boltzmann Statistics
----------------------------------------

The Maxwell-Boltzmann statistics (or the Maxwell-Boltzmann sample space) occurs frequently in the study of natural phenomena. It concerns the placement of balls into boxes and the number of possible placements.

Given a set of $k$ indistinguishable balls ($B$) and a set of $n$ boxes, numbered $1,2,...,n$, ($U$),  we define

* a sample point $\omega$ to be a function from the set $B$ to the set $U$;
* the sample space $\Omega$ to be the set of all functions from the set $B$ to the set $U$; and
* the family of events ${\cal E}$ to be all subsets of $\Omega$.

In addition, the occupation number $\theta_{i}(\omega)$ is the number
of balls in the $i^{th}$ box for the sample point $\omega$. The sample
space $\Omega$ is finite and consists of $n^{k}$ sample points. In the
absence of further information, we assign an equal probability to each
event. Let $A$ be any event. Then we have

$$\begin{eqnarray*}
P(\omega) & = & \frac{1}{n^{k}}\\
P(A) & = & \sum_{\omega \in A} P(\omega)\\
P(\theta_{i}=0) & = & \frac{(n-1)^{k}}{n^{k}}
\end{eqnarray*}$$

**Problem 1:** What is the probability that all the boxes are occupied?

Let $A$ be the event that all boxes are occupied. Let $A_{i}$ be the
event that the $i^{th}$ box is occupied and $B_{i}$ the event that
$i^{th}$ box is empty. Then we have

$$\begin{eqnarray*}
A & = & A_{1} \cap A_{2} \cap \cdots \cap A_{n}\\
P(A) & = & 1-P(A^{c})\\
A^{c} & = & A_{1}^{c} \cup  A_{2}^{c} \cup \cdots \cup A_{n}^{c}\\
& = & B_{1} \cup B_{2} \cup \cdots \cup B_{n}
\end{eqnarray*}$$

Using the inclusion exclusion principle, we have

$$
P(A^{c}) = \sum_{i=1}^{n}P(B_{i}) - \sum_{1 \leq i < j \leq n}P(B_{i} \cap B_{j}) + \sum_{1 \leq i < j < k \leq n}P(B_{i} \cap B_{j} \cap B_{k}) - \ldots
$$

Now,

$$\begin{eqnarray*}
P(B_{i}) & = & \frac{(n-1)^{k}}{n^{k}}\\
P(B_{i} \cap B_{j}) & = & \frac{(n-2)^{k}}{n^{k}}\\
P(B_{i} \cap B_{j} \cap B_{k}) & = & \frac{(n-3)^{k}}{n^{k}}
\end{eqnarray*}$$

Therefore,

$$\begin{eqnarray*}
P(A^{c}) & = & n \cdot \frac{(n-1)^{k}}{n^{k}} - { {n}\choose{2}} \cdot \frac{(n-2)^{k}}{n^{k}} + { {n}\choose{3}} \cdot \frac{(n-3)^{k}}{n^{k}} - ...\\
& = & n \cdot \frac{(n-1)^{k}}{n^{k}} - \frac{n(n-1)}{1 \cdot 2}\frac{(n-2)^{k}}{n^{k}} + \frac{n(n-1)(n-2)}{1 \cdot 2 \cdot 3}\frac{(n-3)^{k}}{n^{k}} - ...
\end{eqnarray*}$$

**Problem 2:** What is the probability that there is no more than one ball in any box?

This problem can be phrased differently. What is the probability that given $k$ persons no two share the same birthday?

Let C be the event that all $\theta_{i} \leq 1$. The number of ways of
placing $k$ balls into $n$ boxes in such a way that no box has more
than one ball $= n(n-1)(n-2) \cdots (n-k+1) = \frac{n!}{(n-k)!}$. The
number $\frac{n!}{(n-k)!}$ is called a falling factorial and denoted
$(n)\_k$.  Therefore $P(C) = \frac{(n)_{k}}{n^{k}}$.

**Aside:** The falling factorial $(n)\_k$ is related to the binomial
coeffient by the relation ${n\choose k} = \frac{(n)\_{k}}{k!}$.
The falling factorial obeys the binomial theorem:  $(n+m)\_{k} =
\sum\_{i=0}^{k}{k\choose i}(n)\_{i}(m)_{k-i}$.
