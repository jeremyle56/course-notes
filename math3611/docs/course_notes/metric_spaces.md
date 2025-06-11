# Metric Spaces

??? note "Course Material"

    === "Lecture 3 - 11/06"

        <div>
        <object data="../../assets/lecture_notes/11062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
        <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
        </object>
        </div>

Recall the definition of a limit $\lim_{x \to a} f(x) = b$ means that "for any number $\epsilon > 0$, there is a number $\delta(\epsilon)$ such that $|f(x) - b| < \epsilon$ whenever $|x - a| < \delta$".

## What is a metric space?

A __metric space__ is a pair $(X, d)$, where $X$ is a (non-empty) set and $d: X \times X \to [0, \infty)$ is a function, such that the following conditions hold for all $x, y, z \in X$:

1. $d(x, y) = 0$ if and only if $x = y$
2. $d(x, y) = d(y, x)$
3. $d(x, y) + d(y, z) \geq d(x, z)$ (_triangle inequality_)

!!! example "Examples"

    The following are examples of metric spaces (proofs have not been included):

    - $X = \mathbb{R}; d(x, y) = |x - y|$ is a metric space.
    - $X = \mathbb{R}^n; d_p((x_1, \dots, x_n), (y_1, \dots, y_n)) = (\sum_{k = 1}^n |x_k - y_k|^p)^{\frac{1}{p}}$, where $p \geq 1$ is a fixed number.
    - $X = \mathbb{R}^n; d_\infty ((x_1, \dots, x_n), (y_1, \dots, y_n)) = \max\{ |x_1 - y_1 |, \dots, |x_n - y_n|\}$.
    - $X$ is any (non-empty) set, and $d(x, y) = \begin{cases} 0 & \text{if } x = y \\
    1 & \text{if } x \neq y \end{cases}$ which is the _discrete_ metric.
    - Let $X = c_{00} = \{(x_n) : x_n = 0 \text{ all but finitely many} n\}$, the set of infinite sequences without only finitely many non-zero coordinates. Define metrics $d_p, p \geq 1$ and $d_\infty$ in a similar way as for $\mathbb{R}^n$.
    - Let $X = C[0, 1]$, the set of continuous real-valued functions on the interval $[0, 1]$. For fixed $p \geq 1$, define

    \[
        d_p(f, g) = \left(\int_0^1 |f(x) - g(x)|^p \, dx \right)^{\frac{1}{p}} \quad \text{ and } \quad d_\infty (f, g) = \sup_{x \in [0, 1]} |f(x) - g(x)|.
    \]

    - Let $(X, d)$ be any metric space, and let $Y$ be any (non-empty) subset of $X$. Then $d / Y \times Y$ is a metric on $Y$ (_subset metric_).

!!! failure "Non-examples"

    There are also a few non-examples of metric spaces (proofs not included):

    - $X = R[0, 1]$, the set of Riemann integrable functions on $[0, 1]$, with $d_1$. This fails axiom 1 with $f(0) = 1, f(x \neq 0) = 0$.
    - $X = \mathbb{R}^2$ with "$d_{\frac{1}{2}}$".
    - The set of all international airports with "flying time metric" or "flight prince metric". Not symmetric.
    - $X = \mathbb{R}^{[0, 1]}$ (the set of real-valued functions on $[0, 1]$), with "$d_\infty$". $d_\infty$ isn't always defined on discontinuous function.

## Sequences

A sequence in a set $X$ is a function from $\mathbb{N}$ (or $\mathbb{Z}_+$) to $X$. (Notation: $\{x_n \}_{n = 0}^\infty$)

Recall: a sequence $\{x_n \}_{n = 0}^\infty \subset \mathbb{R}$ converges to a limit $x \in \mathbb{R}$ if for every $\epsilon > 0$, there is a $K(\epsilon) \in \mathbb{N}$ such that $|x_n - x| < \epsilon$ whenever $n > K(\epsilon)$.

__Theorem:__ A sequence in a metric space can have at most one limit.