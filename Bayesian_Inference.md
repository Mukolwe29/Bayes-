# New Markdown File
# Problem 2: Medical Test

## Posterior Probability with Conditionally Independent Test Results

Given:
- $D$: Omer has the disease.
- $T_j$: Omer tests positive on the  $j$-th test.
- $p = P(D)$: Prior probability that Omer has the disease.
- $a_0 = P(T_j \mid D)$: Probability of testing positive given that Omer has the disease.
- $b_0 = P(T_j \mid D^c)$: Probability of testing positive given that Omer does not have the disease.

We need to find the posterior probability that Omer has the disease given that he tests positive on all $n$ tests.

Since the test results are conditionally independent given Omer's disease status:
$$
P(T_1 \cap T_2 \cap \ldots \cap T_n \mid D) = (a_0)^n
$$
$$
P(T_1 \cap T_2 \cap \ldots \cap T_n \mid D^c) = (b_0)^n
$$

Using Bayes' theorem, the posterior probability is:
$$
P(D \mid T_1 \cap T_2 \cap \ldots \cap T_n) = \frac{P(T_1 \cap T_2 \cap \ldots \cap T_n \mid D) P(D)}{P(T_1 \cap T_2 \cap \ldots \cap T_n)}
$$

Where the denominator is:
$$
P(T_1 \cap T_2 \cap \ldots \cap T_n) = P(T_1 \cap T_2 \cap \ldots \cap T_n \mid D) P(D) + P(T_1 \cap T_2 \cap \ldots \cap T_n \mid D^c) P(D^c)
$$

$$
P(T_1 \cap T_2 \cap \ldots \cap T_n) = (a_0)^n p + (b_0)^n (1 - p)
$$

Therefore, the posterior probability becomes:
$$
P(D \mid T_1 \cap T_2 \cap \ldots \cap T_n) = \frac{(a_0)^n p}{(a_0)^n p + (b_0)^n (1 - p)}
$$

## Posterior Probability with Genetic Condition

Given:
- $G$: Omer has the gene that makes him always test positive.
- $P(G) = \frac{1}{2}$
- $D$ and $G$ are independent.
- If $G$, then $P(T_j \mid G) = 1$.
- If $G^c$, then $a_1 = P(T_j \mid D, G^c)$ and $b_1 = P(T_j \mid D^c, G^c)$.

We need to find the posterior probability that Omer has the disease given that he tests positive on all $n$ tests, considering the gene condition.

Using Bayes' theorem and considering the gene condition, the posterior probability is:
$$
P(D \mid T_1 \cap T_2 \cap \ldots \cap T_n) = \frac{P(T_1 \cap T_2 \cap \ldots \cap T_n \mid D, G^c) P(D, G^c) + P(T_1 \cap T_2 \cap \ldots \cap T_n \mid D, G) P(D, G)}{P(T_1 \cap T_2 \cap \ldots \cap T_n)}
$$

But since $D$ and $G$ are independent:
$$
P(D, G^c) = P(D) P(G^c) = p \cdot \frac{1}{2}, \quad P(D, G) = P(D) P(G) = p \cdot \frac{1}{2}
$$

Similarly, for $D^c$:
$$
P(D^c, G^c) = (1 - p) \cdot \frac{1}{2}, \quad P(D^c, G) = (1 - p) \cdot \frac{1}{2}
$$

Given $G$:
$$
P(T_1 \cap T_2 \cap \ldots \cap T_n \mid G) = 1
$$

Given $G^c$, the tests are conditionally independent as described in part 1.

The denominator becomes:
$$
P(T_1 \cap T_2 \cap \ldots \cap T_n) = P(T_1 \cap T_2 \cap \ldots \cap T_n \mid D, G^c) P(D, G^c) + P(T_1 \cap T_2 \cap \ldots \cap T_n \mid D^c, G^c) P(D^c, G^c) + P(T_1 \cap T_2 \cap \ldots \cap T_n \mid G) P(G)
$$

$$
P(T_1 \cap T_2 \cap \ldots \cap T_n) = (a_1)^n \cdot \frac{p}{2} + (b_1)^n \cdot \frac{1 - p}{2} + 1 \cdot \frac{1}{2}
$$

Therefore, the posterior probability of having the disease is:
$$
P(D \mid T_1 \cap T_2 \cap \ldots \cap T_n) = \frac{(a_1)^n \cdot \frac{p}{2}}{(a_1)^n \cdot \frac{p}{2} + (b_1)^n \cdot \frac{1 - p}{2} + \frac{1}{2}}
$$

## Posterior Probability of Having the Gene

Using the same setup as in part 2, we need to find the posterior probability that Omer has the gene given that he tests positive on all $n$ tests.

The posterior probability is:
$$
P(G \mid T_1 \cap T_2 \cap \ldots \cap T_n) = \frac{P(T_1 \cap T_2 \cap \ldots \cap T_n \mid G) P(G)}{P(T_1 \cap T_2 \cap \ldots \cap T_n)}
$$

$$
P(G \mid T_1 \cap T_2 \cap \ldots \cap T_n) = \frac{1 \cdot \frac{1}{2}}{(a_1)^n \cdot \frac{p}{2} + (b_1)^n \cdot \frac{1 - p}{2} + \frac{1}{2}}
$$