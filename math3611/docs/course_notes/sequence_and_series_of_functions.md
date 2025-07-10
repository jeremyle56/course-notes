# Sequences and Series of Functions

??? note "Course Material"

    === "Lecture 9 - 02/07"

        1. Sequences of functions may converge pointwise or uniformly; uniform convergence is stronger (see page 6).
        2. The difference between pointwise and uniform convergence lies in the order of quantifiers in the epsilon definition.
        3. The Banach space $B(X, E)$ consists of bounded functions $f:X \to E$ with the sup norm.
        4. Uniform limits in $C[0,1]$ stay in $C[0,1]$; pointwise limits may not (see page 11).
        5. Lp-convergence (for $p \geq 1$) can differ from pointwise or uniform convergence (see pages 13–14); on bounded intervals, uniform implies $L^p$, but not vice versa.
        6. In Banach spaces, absolute convergence implies convergence.
        7. The Weierstrass M-test ensures uniform convergence of series in $C[a,b]$ or $Cb(R)$.
        8. It was used by Weierstrass to construct a nowhere differentiable continuous function.
        9. A series of differentiable functions may converge to a non-differentiable limit unless the derivatives converge absolutely.

        ??? abstract "02/07 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/02072025-02-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
            </object>
            </div>

## Types of Convergence

A sequence of numbers $\{x_n \}_{n = 1}^\infty \subset \mathbb{R}$ converge to a number $x$ if:

\[
\text{"for every } \epsilon > 0, \text{ there is a } K(\epsilon) \in \mathbb{N} \text{ such that } |x_n - x| < \epsilon \text{ when } n \geq K \text{."}
\]

**Definition:** A sequence of functions $f_n: X \to \mathbb{R}$ converges **pointwise** to $f$ if for every $x \in X$ and $\epsilon > 0$, there is a $K(x, \epsilon) \in \mathbb{N}$ such that $|f_n(x) - f(x)| < \epsilon$ when $n \geq K$.

**Definition:** A sequence of functions $f_n: X \to \mathbb{R}$ converges uniformly to $f$ if for every $\epsilon > 0$, there is a $K(\epsilon) \in \mathbb{N}$ such that for every $x \in X, |f_n(x) - f(x)| < \epsilon$ when $n \geq K$.

## Bounded Functions

**Uniform Norm:** Let $X$ be a set, and let $B(X, \mathbb{R})$ denote the set of bounded real-valued functions on $X$. The uniform norm is

\[
\lVert f \rVert_\infty = \sup_{x \in X} |f(x)|.
\]

**Theorem:** $(B(X, \mathbb{R}), \lVert \cdot \rVert_\infty)$ is a Banach space.

Let $X$ be a set and let $E$ be a Banach space. Then $B(X, E)$ (bounded $E$-valued functions) is a Banach space with the uniform norm. If $X$ is a metric space, then so is $C_b(X, E)$ (continuous bounded $E$-valued functions).

Let $\{f _n \}_{n = 1}^\infty$ be a sequences of Riemann integrable functions on an interval $[a, b]$. We say that the sequence **converges in $L^p$, for some $p \geq 1$, to an integrable function $f$ if

\[
    \lim_{n \to \infty} \int_a^b |f_n(x) - f(x)|^p \, dx = 0.
\]

## Series of Functions

If $\{ x_n \}_{n = 0}^\infty$ is a sequence of numbers, then we write $\sum_{n = 0}^\infty x_n$ for the corresponding series (meaning sequence of partial sums and/or its limit!).

Similarly, if $\{f_n(x) \}_{n = 0}^\infty$ is a sequence of functions, we can consider the corresponding series $\sum_{n = 0}^\infty f_n(x)$.

A series $\sum_{n = 0}^\infty x_n$ **converges absolutely** if $\sum_{n = 0}^\infty |x_n|$ converges. Recall: If a series converges absolutely, then it converges.

**Theorem (Absolute convergence implies convergence):** Let $E$ be a Banach space. let $\{ x_n \}_{n = 0}^\infty$ be a sequence of vectors in $E$ whose series of norms $\sum_{n = 0}^\infty \lVert x_n \rVert$ converges (in $\mathbb{R}$). Then the series of vectors $\sum_{n = 0}^\infty x_n$ converges (in $E$). 

**Corollary (Weierstrass M-Test):** Let $\{ f_n \}_{n = 0}^\infty$ be a sequence of real-valued functions on a set $X$. Suppose that there is a sequence of numbers $M_n >\geq 0$ such that $M_n$ is an upper bound for $f_n$ for each $n$, and such that the series $\sum_{n =0 }^\infty M_n$ converges. Then t he series of functions $\sum_{n = 0}^\infty f_n$ converges uniformly.

**Theorem:** Let $\{ f_n \}_{n = 1}^\infty \subseteq C[a, b]$ be a sequence of functions which converges uniformly to $f$. Then $\int_a^b f_n(x) dx$ converges to $\int_a^b f(x) dx$.

## Uniform Limits and Differentiation

**Theorem:** Let $\{ f_n \}_{n = 1}^\infty \subseteq C[a, b]$ be a uniformly convergent sequence of functions. Suppose that functions $f_n$ are all differentiable on $(a, b)$, with continuous and bounded derivatives $f_n'$. Suppose further that the sequence of derivatives $\{ f_n' \}_{n = 1}^\infty$ converges uniformly on $(a, b)$.

Then the limit function $f$ is also differentiable on $(a, b)$, and $f'$ is the uniform limit of the sequence $\{ f_n' \}_{n = 1}^\infty$.

**Corollary:** Suppose $f_n$ is a sequence of continuously differentiable functions on an interval $(a, b)$, and suppose that both the series

\[
    f(x) = \sum_{n = 0}^\infty f_n(x) \quad \text{ and } \quad g(x) = \sum_{n = 0}^\infty f_n'(x)
\]

converge uniformly. Then $f(x)$ is differentiable, and we have $f'(x) = g(x)$.

Let $\sum_{n = 0}^\infty a_n x^n$ be a power series, and suppose the sequence $\{|a_n|^{\frac{1}{n}}\}_{n = 0}^\infty$ is bounded. For each $n \geq 0$, let

\[
    b_n = \sup\{|a_n|^{\frac{1}{n}}, |a_{n + 1}|^{\frac{1}{n + 1}}, |a_{n + 2}|^{\frac{1}{n + 2}}, \dots\}.
\]

and let 

\[
    b = \lim_{n \to \infty} b_n
\]

($b$ is the **limit superior** or **lim sup** of the sequence $\{|a_n|^{\frac{1}{n}}\}_{n = 0}^\infty$).

**Theorem (Cauchy-Hadamard):** With notation as above, the power series converges absolutely if $|x| \cdot b < 1$ and diverges if $|x| \cdot d > 1$. (True for complex numbers as well!)

**Definition:** The number $R = \frac{1}{b}$, for $b \neq 0$, is called the **radius of convergence** of the power series. If $b = 0$ the radius of convergence is said to be $\infty$. If the sequence $\{|a_n|^\frac{1}{n}\}_{n = 0}^\infty$ is unbounded, then the radius of convergence is said to be $0$.

**Corollary:** Let $\sum_{n = 0}^\infty a_n x^n$ be a power series, with radius of convergence $R$. Then the termwise derivative power series $\sum_{n = 1}^\infty n \cdot a_n x^{n - 1}$ has the same radius of convergence $R$.

**Theorem:** Let $\sum_{n = 0}^\infty a_n x^n$ be a power series, with radius of convergence $R > 0$. Then the series is differentiable on the interval $(-R, R)$, with the derivative given by $\sum_{n = 1}^\infty n \cdot a_n x^{n - 1}$.