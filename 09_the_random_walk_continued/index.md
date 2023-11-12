---
layout: lecture
title: The random walk
lecture: 9
date: Monday, February 22, 1999
transcriber: Yvonne Lai and David Wang
---

### On Friday's Random Walks
On Friday, you all saw random walks. Here is a quick summary of what you *should* have gotten out of the lecture...

- $\Omega$ = all possible paths.
- Note: a path is simply a sequence (possibly infinite) of $1$s and $-1$s.
- On this $\Sigma$, we can define Random Variables $Y_1, Y_2, \ldots$ that are identically distributed and independent. So, $P(Y_n = 1) = \frac{1}{2}$, $P(Y_n = -1) = \frac{1}{2}$. Here, $Y_n$ is the $n^{th}$ step. The probability distribution is similar to the Rademacher function in measure theory.

Now, there are many random variables that we are interested in, such as:
- $G_n = Y_1 + Y_2 + \ldots + Y_n$ (This is called the *position* at time $n$)
- $Z_a$ = waiting time to reach "level" $a$ (This is how long it takes for a given path to reach a height of $a$)
- $M_n$ = maximum level attained in the first $n$ steps
- And here's a TOUGH Random Variable: Number of sign changes in the first $n$ steps

In order to tackle something like $M_n$ more effectively, we need to develop better techniques than those currently in our toolchest. This last example is a motivation for our next topic: Conditional Probability.

### Conditional Probability
Now, I've stated before that given a sample space $\Omega$ and a family of events $\cal{E}$, we can define a probability measure $P$ on $\cal{E}$. But, I never stated that an event can have only one $P$! Now is the time to adjust our minds to this new idea of conditional probability.

Some handwaving first:

Given $A$, $A \subseteq \Sigma$.

Say the probability of $A$ changes according to whether or not $B$ has occurred. If $B$ has occurred, the only events in $A$ that can occur are those also in $A \cap B$. In other words, the only events that can occur are in $B$.

What if $A$ is the entire sample space? Then $P(A \cap B) = P(\Sigma \cap B) = P(B)$. But this doesn't equal to 1...
Thus, we renormalize:
$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$
This is known as the conditional probability of $A$ given $B$.
It is also called $P_B(A)$, emphasizing that the probability is with respect to $B$.

In renormalizing, we have thus created a new probability in the sample space $\Sigma$. In fact, this new probability satisfies all the axioms of probability on the same sample space of $\Sigma$, $\cal{E}$.

Now, $P_B$ satisfies all the axioms of a probability measure given the same sample space $\Omega$ and $\cal{E}$ that we have already talked about.

Example:

$$
P_B(A^{c}) = 1 - P_B(A)
$$

The left-hand side is:

$$
P_B(A^{c}) = \frac{P(A^{c} \cap B)}{P(B)}
$$

Note that:

$$
P(A^{c} \cap B) + P(A \cap B) = P(B) \\
\frac{P(A^{c} \cap B)}{P(B)} + \frac{P(A \cap B)}{P(B)} = 1 \\
P(A^{c} \mid B) + P(A \mid B) = 1 \\
P(A^{c} \mid B) = 1 - P(A \mid B)
$$

Likewise, the other axioms hold:

$$
P(\emptyset \mid B) = \emptyset \\
P(\Omega \mid B) = 1 \\
P(A_1 \cup A_2 \cup \ldots \mid B) = P(A_1 \mid B) + P(A_2 \mid B) + \ldots \\
\text{if } A_1, A_2, \ldots \text{ are disjoint}
$$

This concept of taking a new probability simply by taking a quotient is amazing! The intuitive concept rendered by this is powerful and useful.

Checking this idea against independence. If $A$ and $B$ are independent, what is $P(A \mid B)$? Intuitively, it should be $P(A)$ because $A$ does not care about $B$.

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{P(A)P(B)}{P(B)} = P(A)
$$

Of course, all this means nothing without examples, so here are some Mickey Mouse examples to illustrate this concept.

### Examples of Conditional Probability
#### Bernoulli Process

We are given a man, his wife, and their two children, and we ask the following questions:
- What's the probability that their first child is a boy? Trivial; it's $\frac{1}{2}$
- What's the probability that their first child is a girl? Well, a girl is just as likely as a boy, so it's $\frac{1}{2}$
- Here's a tougher one. What's the probability that the couple's first child will be a boy if we *know* they have at least one boy? Not so simple now...

So here's how the problem works. Let:
- A = event that the first child is a boy
- B = event that *at least* one child is a boy

It's obvious that $P(B) = \frac{3}{4}$ because with two children, the only way to not have a boy is to have two girls, and that happens 1 out of 4 ways. Thus, the probability that we are interested in, using conditional probability, is:

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{1/2}{3/4} = \frac{2}{3}
$$

#### Maxwell Boltzmann
So now we will do balls and boxes...
What is the probability that a box has $j$ balls in it given that another box has 0 balls in it? Thus, we are interested in:

$$P(\theta_2 = j \mid \theta_1 = 0) = \,?$$

$$
\begin{eqnarray*}
P(\theta_2 = j \mid \theta_1 = 0) &=& \frac{P(\theta_2 = j) \cap (\theta_1 = 0)}{P(\theta_1 = 0)} \\
                                  &=& \frac{ {k \choose j} (n-2)^{k-j} / n^{k}}{(n-1)^{k} / n^{k}} \\
                                  &=& {k \choose j} \frac{(n-2)^{k-j}}{(n-1)^{k}}
\end{eqnarray*}
$$

Of course, one could have done this one without conditional probability. You could have just taken out one box (since its occupancy number is 0) and do the same thing with $n-1$ boxes. The answer comes out the same either way.

#### The Plague
This is a classical, bread-and-butter example of probability. Imagine a plague has just swept over the city, and that the probability that a person in the city has the plague is 10%. Furthermore, let's say that there is a test to determine if a person has the plague or not, and it is *accurate* 80% of the time. So,

- A = event that the patient has the plague
- B = event that the test is *accurate*
- Note: A and B are independent events. The test does not cause the person to have the plague nor affect the person catching the plague.

Now, let:

- C = event that the test is *positive*

What is $P(C)$?

$$
C = (A \cap B) \cup (A^{c} \cap B^{c})
$$

This is obvious, since $C$ occurs only when a patient has the plague and the test is accurate, or the patient does not have the plague and the test is not accurate (false positive). And wonder of wonders, C is also expressed as a union of disjoint sets...

$$
P(A) = 0.1 \\
P(B) = 0.8 \\
P(C) = P(A \cap B) + P(A^{c} \cap B^{c}) = 0.1 \times 0.8 + 0.9 \times 0.2 = 0.26
$$

This result is cute, but it's not really useful. Who cares about the probability that the test is positive in the middle of a plague? No... what people really care about is whether they have the plague given that their test says positive! How do we formulate this burning question? Simple. The people are merely asking for $P(A \mid C)$. So, let's calculate that.

$$
\begin{aligned}
P(A \mid C) &= \frac{P(A \cap C)}{P(C)} \\
            &= \frac{P(A \cap B)}{P(C)} \\
            &= \frac{P(A)P(B)}{P(C)}\\
P(A \mid C) &= \frac{4}{13}
\end{aligned}
$$

Note that:

$$
\begin{aligned}
A \cap C &= A \cap ((A \cap B) \cup (A^{c} \cap B^{c}))\\
         &= (A \cap (A \cap B)) \cup (A \cap (A^{c} \cap B^{c}))\\
         &= (A \cap B) \cup \emptyset\\
         &= A \cap B
\end{aligned}
$$

#### Three Fundamental Properties of Conditional Probability
Well, it's actually two fundamental laws and a very useful third property, but that's not important. Here they are:

**Law of Alternatives**
Given a $\Omega$, we will let $\Pi$ be a partition of $\Omega$ with blocks $B$. Then,

$$
\begin{aligned}
\pi &= \{B\} \\
B, B' &\in \pi \rightarrow B \cap B' = \emptyset \\
P(B) &> 0 \\
P(\bigcup_{B \in \pi} B) &= 1
\end{aligned}
$$

Now, given that $\pi$ is a partition of the sample space $\Omega$, then for any event $A$ we have:

$$
P(A) = \sum_{B \in \pi} P(A \mid B)P(B)
$$

Proof:

$$
\begin{aligned}
\sum_{B \in \pi} P(A \mid B)P(B) &= \sum_{B \in \pi} \frac{P(A \cap B)}{P(B)} P(B) \\
                                  &= \sum_{B \in \pi} P(A \cap B) \\
                                  &= P(\bigcup_{B \in \pi} (A \cap B)) \\
                                  &= P(A \cap \bigcup_{B \in \pi} B) \\
                                  &= P(A \cap \Omega) \\
                                  &= P(A)
\end{aligned}
$$

Note that since B are blocks of the partition $\pi$, they must be disjoint. That allows us to move from a sum of probabilities to a probability of sums.

**Law of Successive Conditioning**

Quite simply, this is:

$$
P(A \cap B) = P(A)P(B \mid A)
$$

Substitute $\frac{P(B \cap A)}{P(A)} = P(B \mid A)$ and you'll get the conclusion. It looks very innocuous, doesn't it? Let's do this for $P(B_1 \cap B_2 \cap B_3)$. Now, we *dream* that the results look something like: $P(B_1)P(B_2 \mid B_1)P(B_3 \mid B_1 \cap B_2)$...

So let's convince ourselves of that.

$$
\begin{aligned}
P(B_1)P(B_2 \mid B_1)P(B_3 \mid B_1 \cap B_2) &= P(B_1)\frac{P(B_1 \cap B_2)}{P(B_1)}\frac{P(B_1 \cap B_2 \cap B_3)}{P(B_1 \cap B_2)}
\end{aligned}
$$

Miracles of miracles, it works out! Next time, we'll see more examples of this.
