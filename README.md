# A tl;dr summary of [The unexpected probability result confusing everyone by Stand-up Maths](https://youtu.be/ga9Qk38FaHM)

Let $n,m \in \mathbb{Z}^+$. Let $\text{rand}(S)$, where $S\subseteq \mathbb{R}$, return a random number from a uniform distribution on the elements of $S$.
Let $\text{d}m$ refer to a dice with sides 1 through $m$ such that rolling the dice produces a uniformly distributed random integer in the inclusive interval $[1,m]$. Then, let $n\text{d}m$ refer to a set of $n$ random numbers produced by $\text{d}m$.
Taking the maximum of the set $n\text{d}m$ is equivalent to taking the $n$th root of a random real number on the interval $[1,m^n]$ then rounding to the nearest integer;

$$\text{max}(n\text{d}m) \equiv \left\lceil \text{rand}([1,m^n]) ^{1/n}\right\rceil .$$

Similarly,

$$\text{min}(n\text{d}m) \equiv \left\lceil 1 - \left(1 - \frac{\text{rand}([1,m^n])}{m^n}\right)^{1/n} \right\rceil .$$

Also notice in the figures, specifically the generation time comparisons, that the equivalent algorithm offers significant time savings *in unrealistic numbers of dice* and more importantly no significant increase in computational cost at *unrealistic* numbers of dice.

It's not rigorous, but it's fine.
