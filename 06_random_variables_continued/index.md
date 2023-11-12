---
layout: lecture
title: Random variables (continued)
lecture: 5
date: Friday, February 16, 1999
transcriber: Bilge Demirköz
---

First, we will give a brief summary of the previous theory. If we have a variable, more precisely an integer variable $X$, then $p(X=n) = p_{n}$ where $p_{n}$ is called the probability distribution.

Given two random variables $X$ and $Y$, they have a joint distribution

$$
P((x=i) \cap (y=j)) = r_{ij}\\
\sum_{j} r_{ij} = p_{i} = P(X=i)\\ 
\sum_{i} r_{ij} = q_{j} = P(Y=j)
$$

Then the expectation value is 

$$
E(x)= \sum_{n} n p_{n}
$$

Note that expectation values add: $E(X+Y)=E(X)+E(Y)$. This is very remarkable since we do not have to compute $E(X+Y)$ directly from the definition of expectation value. Instead, we can just add the expectation values of $X$ and $Y$.

**Maxwell-Boltzmann Statistics:  $ \Omega_{MK} $**

$$
\theta_{i} = \text{occupation number of } i.
$$

Last time, we derived the joint distribution of all occupation numbers, $P((\Theta_{1} = i_{1}) \cap \ldots \cap (\Theta_{n} = i_{n}))$ is equal to

$$ 
\begin{cases} 
0 & \text{if } i_{1}+ i_{2}+ \ldots+i_{n} \neq k\\
\frac{1}{n^{k}} \cdot \binom{k}{i_{1}} \cdot \binom{k-i_{1}}{i_{2}} \cdot \ldots \binom{k-i_{1}-i_{2}-\ldots-i_{n-2}}{i_{n-1}} & \text{otherwise}
\end{cases}
$$

We have $k$ balls and we take away $i_{1}$ and then $i_{2}$ \ldots and so on until the denominator is $i_{n-1}$ and so the multiplication of these binomial terms gives the number of sample points. Now let's simplify this result:

$$
\frac{1}{n^{k}} \cdot \frac{k!}{i_{1}!(k-i_{1})!} \cdot \frac{(k-i_{1})!}{i_{2}!(k-i_{1}-i_{2})!} \cdot \ldots
$$

Miracle! There is a cancellation so we get:

$$
\frac{1}{n^{k}} \cdot \frac{k!}{i_{1}! i_{2}! \ldots i_{n}!} = \frac{1}{n^{k}} \cdot \binom{k}{i_{1}, i_{2}, \ldots , i_{n}}
$$

where $\binom{k}{i_{1}, i_{2}, \ldots , i_{n}}$ is called the multinomial coefficient.

$$
\begin{aligned}
P(\Theta_{1}=i) &= \frac{1}{n^{k}} \cdot (n-1)^{k-i} \cdot \binom{k}{i} \\
E(\Theta_{1}) &= \sum_{i=0}^{k} i \cdot P(\Theta_{1}=i) = \sum_{i=0}^{k} i \cdot \binom{k}{i} \cdot \frac{(n-1)^{k-i}}{n^{k}}
\end{aligned}
$$

But to get the expectation value like this is very hard. Then there must be an easier way of doing it. We are forced to think to get out of calculating this horrible thing.\\
Then we write the probability for $\Theta_{1}$ :

$$
P(\Theta_{2}=i) = \frac{1}{n^{k}} \cdot (n-1)^{k-i} \cdot \binom{k}{i}
$$

Then we notice that $\Theta_{1}$ and $\Theta_{2}$ are statistically the same but they are not the same! They are not identical since they are different boxes after all. We need a new concept; we say that $\Theta_{1}$ and $\Theta_{2}$ are identically distributed. More generally, two random variables, $X$ and $Y$ are identically distributed when $P(X=n)=P(Y=n)$ for all integers n.

If $X$ and $Y$ are identically distributed then their expectation values are the same, that is $E(X)=E(Y)$. Then we have $E(\Theta_{1})= E(\Theta_{2})= \ldots = E(\Theta_{n})$ but $\Theta_{1}+\Theta_{2}+ \ldots +\Theta_{n}$ is a random variable and takes the value of k balls with probability 1. Then,

$$
E(\Theta_{1}+ \Theta_{2}+ \ldots +\Theta_{n})=k= E(\Theta_{1})+ E(\Theta_{2})+ \ldots +E(\Theta_{n})
$$

But all these expectation values, $E(\Theta_{1}), E(\Theta_{2})$, \ldots are equal. The following holds:

$$
\begin{aligned}
E(\Theta_{1}+ \Theta_{2}+ \ldots + \Theta_{n}) &= n \cdot E(\Theta_{1})\\
E(\Theta_{1}) &= \frac{k}{n}
\end{aligned}
$$

We did not have to calculate the hard way! Now let's do something different with Maxwell-Boltzmann Statistics:

$$
\begin{aligned}
X_{1} &= \text{position of ball } 1.\\
P(X_{1}=i) &= \frac{1}{n} \text{ where } i=1,2,3,\ldots \text{ since all the boxes are identical.}\\
X_{2} &= \text{position of ball } 2.\\
P(X_{2}=i) &= \frac{1}{n}\\
\end{aligned}
$$

Then  $X_{1}$ and $X_{2}$ are identically distributed and they are also independent variables. Let's check that they are indeed independent.

$$
P((X_{1}) \cap (X_2)) = \frac{1}{n^2} = P(x_1 =i) \cdot P(x_2 =j)
$$

Here is a tough random variable: $N =$ number of empty boxes. In real life, this random variable comes up for computers, placing people into cubicles and so on.

**Example 5 : The Bernoulli Process**

We toss a biased coin with a bias $p$, infinitely many times. 

$$
\begin{aligned}
\Omega &= \text{all } \infty \text{ sequences of } 0 \text{'s and } 1 \text{'s.} \\
T_1 &= \text{waiting time for the first head.} \\
P(T_1=n) &= ? \\
\end{aligned}
$$

We have to have all tails as the first $n-1$ outcomes. Then it will look like: 

$$
\{ ( 0, 0, 0, \ldots 0, 1, w_{n+1}, w_{n+2}, \ldots) \}
$$

We have $n-1$ $0$'s before we have a $1$. Then we have 

$$
P(T_1=n)= q^{n-1} \cdot p
$$

Now observe two facts:
- As expected, $ \sum_{n>0}  q^{n-1} \cdot p =1 $ . This is automatically so but 

$$
\sum_{n>0}  q^{n-1} = 1+ q+q^2+ \ldots = \frac{1}{1-q} = \frac{1}{p}
$$

Of course, we do not need to do this since we already know that the sum of all probability distributions has to equal 1.
- But there is a kinkyness about this random variable since $T_1$ is not defined on $w=(0, 0, 0, \ldots)$ but $P(w)=0$. 

Let's look at another example:

$$
\begin{aligned}
T_2 = \text{gap between the first and the second head.} \\
P(T_1=k) \cap P(T_2=n)= ?
\end{aligned}
$$

The second head must occur at the $k+n^{th}$ event since it looks like this:

$$
\{ ( 0, 0, 0, \ldots 0, 1, 0, 0, \ldots 1,  w_{n+k+1}, w_{n+k+2}, \ldots) \}
$$

Then we will have:

$$
P(T_1=k) \cap P(T_2=n)= q^{k-1} \cdot p \cdot q^{n-1} \cdot p  
$$

Going back to calculate $T_2$, we find:

$$
(T_2 =n)=(\cup_{k}(T_1=k))\cap(T_2=n)= \cup_{k}((T_1=k)\cap(T_2+n))
$$

from the distributive law. It is a union of disjoint events so we get:

$$
\sum_{k}P(T_1=k) \cap P(T_2=n)=\sum_{k}q^{k-1} \cdot p \cdot q^{n-1}
\cdot p = q^{n-1} \cdot p
$$

since $ q^{k-1} \cdot p = 1$. Then $T_1$ and $T_2$ are independent
variables. We should have known this earlier since the coin does not
know whether it is at the beginning of a run or somewhere else. Still,
it was not intuitively obvious.
Let's look at another example:

$$
X_{n}= \text{outcome of the $n^{th}$ toss} = \left\{
\begin{array}{rcl}
1 & \text{with probability } p\\
0 & \text{with probability } q
\end{array} \right\}
$$

The random variables $X_1$, $X_2$, $X_3$,\ldots are independent and
are identically distributed. Now it is too easy. Let's toughen it up a
little bit. Let $S_n$ be the number of heads in the first $n$ tosses
then we have,

$$
\begin{eqnarray}
X_1 + X_2 + \ldots + X_n &=& S_n\\
P(S_n=k) &=& \binom{n}{k} \cdot p^k \cdot q^{n-k}
\end{eqnarray}
$$ 

from the binomial distribution.

$$
\sum_{k=0}^{n}P(S_n=k)= 1 = \sum_{k=0}^{n}\binom{n}{k} \cdot
p^k \cdot q^{n-k} = (p+q)^{n}
$$

And so we have proved the binomial theorem for the second time. 
What about $E(S_n)$? We will do that next time, using a trick.
