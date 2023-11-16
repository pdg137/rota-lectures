---
layout: lecture
title: Bayes's Law (continued)
lecture: 14
date: Monday, March 10, 1999
transcriber: Luis Benitez
---

Suppose we have an *urn* with $n$ balls, and $j$ balls are red. The other $n-j$ balls are black. From that urn we take a sample of $k$ balls. Let us define the following event:

- A = number of red balls in the sample $k$.

By combinatorial probability we can write:

$$
P(A=i)=\frac{ { {j}\choose{i}}{ {n-j}\choose{k-i}}}{ { {n}\choose{k}}}
$$

This is called the *Hypergeometric distribution*. In real life this doesn't happen since we don't know $j$. So, how do we set up a sample space? We use the *Law of Alternatives*.

If we don't know the number of red balls in the urn, but we know both $n$ & $k$, then the only way to define a sample space is by the Law of Alternatives.

$$
P(A=i) = \sum_{j=0}^{n} P(A \mid U = j) P(U = j)
$$

The first term of the summation is called the *likelihood*. The second term is called the *prior*. The prior requires an arbitrary assignment. Guess work is necessary here. This guess is what is called the prior. Having chosen a prior we have a sample space, hence

$$
\begin{align*}
P(U=j \mid A=i) &= \frac {P(U=j) \cap P(A=i)}  {P(A=i)}\\
               &= \frac {P(A=i \mid U=j) P(U = j)} {P(A=i)}
\end{align*}
$$

The denominator is the *normalization coefficient*. And we have defined this earlier so we substitute in and get,  
$\frac {P(A=i \mid U=j) P(U=j)} {\sum_{j=0}^{n} P(A=i \mid U=j)P(U=j)}$

This way we can display the prior and the likelihood both in the denominator and in the numerator. We can take this and divide it into two cases:

- $U$ = number of red balls in urn
- $A$ = number of red balls in sample of $k$

*Case 1: Uniform Prior*  
$P(U = j) = \frac {1} {n+1}$ for all $0 \leq j \leq n$

With this assumption we found that the probability:

$$
P(U=j \mid A=i) = \frac { {j\choose i}{ {n-j}\choose{k-i}}}{ { {n+1}\choose{k+1}}}
$$

given total ignorance about the total number of $j$. If we extract nothing then $i=0$ and $k=0$, therefore we get:
$$
P(U=j \mid A=i) = \frac {1} {n+1}
$$

When we extract only 1 ball and it is red, then $k=1$ and $i=1$, hence:

$$
P(U=j \mid A=i) = \frac{ { {j}\choose {1}}} { { {n+1}\choose {2}}} = \frac {2j}{(n+1)n}
$$

$$
\sum_{j=0}^{n} P(U=j \mid A=1) = \sum_{j=0}^{n} P_{(A=1)} (U=j) = 1
$$

which is the sum of all random variables so,

$$
\sum_{j=0}^{n} \frac{2j}{n(n+1)} = 1\\
\sum_{j=0}^{n} j = \frac{n(n+1)}{2}
$$

as in high school.

*Case 2: Conjugate Prior*

$$
P(U=j) = P (X_1 + X_2 + ...+ X_n = j) = P(S_n = j) = {n\choose j} p^j q^{n-j}
$$

$X_i$'s are the Bernoulli Random Variables. We take the final result as a prior and plug into Baye's formula. The posterior is then
$$
P(U=j \mid A=i) = { {n-k}\choose{j-i}}p^{j-i} q^{n-k-(j-i)}
$$
What does this tell us? We take and set $j=i+r$, since $j \neq s$.

$$ 
P(U=i+r \mid A=i) = { {n-k}\choose{r}}p^r q^{n-q-r}
$$

This reproduces itself, hence the name of conjugate prior. Let's do now the same problem with replacement, which is easier to think about, but the result is messier.

*Baye's Sampling with Replacement*

Again, in an urn with $j$ red balls and $n-j$ black balls

$$
P(A=i \mid U=j) = {k\choose i} \left(\frac{j}{n}\right)^i \left( \frac{n-j}{n} \right)^{k-i}
$$

$$
P(U=j \mid A=i) = \frac{ { {k} \choose {i}} \left(\frac{j}{n} \right)^i
\left(\frac{n-j}{n} \right)^{k-i} P(U=j)}{\sum_{j=0}^{n} { {k}\choose {i}} \left( \frac{j}{n}^i\right)\left( \frac{n-j}{n} \right)^{k-i} P(U=j)}
$$

$$
                = \frac{\left( \frac{j}{n} \right)^i \left( \frac{n-j}{n} \right)^{k-i}P(U=j)}{\sum_{j=0}^{n} \left( \frac{j}{n} \right)^i \left(\frac{n-j}{n} \right)^{k-i}P(U=j)}
$$

Again, we can divide the problem into two cases.

*Case 1: Uniform Prior*

$P(U=j) = \frac {1}{n+1}$ for $0 \leq j \leq n$

The posterior is then given by

$$
P(U=j \mid A=i) = \frac {\left( \frac{j}{n}\right)^i \left(\frac{n-j}{n}\right)^{k-i}}{\hbox{mess}}
$$

We don't need to know what "mess" is because as we have said before, it is just a normalization factor. Therefore, we can write

$$
P(U=j \mid A=i) \propto \left( \frac{j}{n}\right)^i \left(\frac{n-j}{n}\right)^{k-i}
$$

*Case 2: Conjugate Prior*

From before, we can just say

$$
P(U=j) \propto \left(\frac{j}{n}\right)^t \left(\frac{n-j}{n}\right)^{r-t}\\
$$

and the posterior (as before but with the change of proportionality) is given by

$$
P(U=j \mid A=i) \propto \left(\frac{j}{n}\right)^i \left(\frac{n-j}{j}\right)^{k-i} \left(\frac

{j}{n}\right)^t \left(\frac{n-j}{n}\right)^{r-t}
$$

$$
                 \propto \left(\frac{j}{n}\right)^{i+t} \left(\frac{n-j}{n} \right)^{k+r-i-t}
$$

