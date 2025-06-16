# Metric Spaces

??? note "Course Material"

    === "Lecture 3 - 11/06"

        1. __Definition of a metric space__ and __axioms of a metric__:
            - __Non-negativity and exactness__: $d(x, y) \geq 0$, and $d(x, y) = 0$ if and only if $x = y$.
            - __Symmetry__: $d(x, y) = d(y, x)$
            - __Triangle inequality__: $d(x, z) \leq d(x, y) + d(y, z)$
        2. The __absolute value__ defines a metric on the real numbers: $d(x, y) = |x - y|$.
        3. The $d_p$ metric on the space of $n$-tuples $\mathbb{R}^n$.
            - The triangle inequality in this case is known as the __Minkowski inequality__.
            - The proof is non-trivial and relies on __Hölder's inequality__, which is itself proved using __Young's inequality__.
        4. The __discrete metric__ defines a metric on any set: $d(x, y) = 1$ if $x \neq y$, and $0$ otherwise.
        5. The space $c_{00}$ (sequences with finitely many non-zero terms) is a metric space under the $d_p$ metric:
            - There is no issue with convergence, as all sequences in $c_{00}$ are eventually zero.
        6. The set of continuous functions $C[0, 1]$ becomes a metric space with the integral version of the $d_p$ metric:

            \[
                d_p(f, g) = \left(\int_0^1 |f(x) - g(x)|^p \, dx \right)^{1/p}
            \]

            - The triangle inequality follows a similar argument to the finite-dimensional case $\mathbb{R}^n$.

        7. A __subset__ of a metric space becomes a __metric subspace__ when equipped with the restricted metric.
        8. The set of __Riemann integrable functions__ is __not__ a metric space under the $d_p$ metric, as it may fail the exactness axiom.
        9. The $d_{1/2}$ function is __not__ a metric, as it fails the triangle inequality.
        10. The $d_{\infty}$ (supremum) metric:
            - Is valid on $\mathbb{R}^n: d_{\infty} (x, y) = \max_i |x_i - y_i|$
            - May not be defined on functions over $[0, 1]$ if there are unbounded.
            - On __bounded functions__, it is a metric; the triangle inequality relies on the definition of the supremum.
        11. The __definition of the limit of a sequence__ extends to metric spaces:
            - $x_n \to x$ if for every $\epsilon > 0$, there exists $N$ such that $d(x_n, x) < \epsilon$ for all $n > N$.
        12. __Limits are unique__ in metric spaces: a sequence cannot converge to two different points.

        ??? abstract "11/06 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/11062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
            </object>
            </div>

    === "Lecture 4 - 12/06"

        1. We can extend the __definition of the limit of a function__ in the context of metric spaces using sequences.
            - In this setting, we say the function is __sequentially continuous__ if it preserves limit of sequences.
        2. We define an $\epsilon$-ball in a metric space as:

            \[
                B(x, \epsilon) = \{y \in X \mid d(x, y) < \epsilon \}
            \]

        3. The statement of a __limit of a sequence__ $x_n \to x$ in a metric space can be __reduced to a numerical sequence $d(x_n, x) \to 0$.
        4. Once the $\epsilon$-ball is defined, we can introduce key topological concepts:
            - __Interior points__: points that belong to some $\epsilon$-ball fully contained in the set
            - __Boundary points__: points where every $\epsilon$-ball insects both the set and its complement
        5. Using these, we define:
            - __Open sets__: sets where all points are interior
            - __Closed sets__: sets that contain all their boundary points
        6. The set of __interior points__ of a set $Y$, denoted $\mathrm{Int}(Y)$, is always __open__.
            - The proof is non-trivial: it involves careful reasoning about set identities and a clever use of the triangle inequality.
        7. The __closure__ of a set is defined as the union of its interior and boundary:

            \[
                \mathrm{Cl}(Y) = \mathrm{Int}(Y) \cup \mathrm{Bd}(Y)
            \]

        8. A set is said to be __dense__ if its closure equals the entire metric space:

            \[
                \mathrm{CI}(Y) = X
            \]

        9. The space $c_{00}$ (sequences with finitely many non-zero terms) provides a challenging example:
            - The __interior of__ $c_{00}$ is empty under the $d_\infty$ metric.
            - The __interior of its complement__ requires introducing the space $c_0$, the set of sequences that converge to zero.

        ??? abstract "12/06 Lecture Slides"

            <div>
                <object data="../../assets/lecture_notes/12062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
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

<!-- !!! example

    For metric spaces $X$ and $Y$, a function $f: X \to Y$ is said to be __sequentially continuous__ if for every convergent sequence $\{ x_0 \}_{n = 0}^\infty \subseteq X$ with limit $x$, the sequences $\{ f(x_n) \}_{n = 0}^\infty$ converges to $f(x)$ (in $Y$) -->

## Topology of Metric Spaces

For a point $x$ in a metric space $(X, d)$ and a number $\epsilon > 0$, define the (open) __$\epsilon$-ball__

\[
    B(x, \epsilon) = \{ y \in X : d(y, x) < \epsilon \}
\]

!!! example

    - For $X = \mathbb{R}^2, d = d_1(\mathbf{x}, \mathbf{y}) = |x_1 - y_1| + |x_2 - y_2|$ then $B(\mathbf{0}, 1) = \{ \mathbf{x} \in \mathbb{R}^2 : |x_1| + |x_2| < 1 \}$.
    - For $X = \mathbb{R}^2, d = d_2$ then $B(\mathbf{0}, 1) = \{ \mathbf{x} \in \mathbb{R}^2 : |x_1|^2 + |x_2|^2  < 1 \}$.
    - For $X = \mathbb{R}, d = |\cdot|$-value then $B(a, \epsilon) = \{ x \in \mathbb{R} : |x - a| < \epsilon \}$.

Let $(X, d)$ be a metric space, and consider $Y \subseteq X$. Define the __interior__

\[
    \mathrm{Int}(Y) = \{ y \in Y: \exists \epsilon > 0 \text{ such that } B(y, \epsilon) \subseteq Y \}
\]

Define the __boundary__

\[
    \mathrm{Bd}(Y) = X \setminus (\mathrm{Int}(Y) \cup \mathrm{Int}(Y^c)).
\]

Then we can write $X = \mathrm{Int}(Y) \cup \mathrm{Bd}(Y) \cup \mathrm{Int}(Y^c)$.

!!! example

    Show that $x \in \mathrm{Bd}(Y)$ if and only if $\forall \epsilon > 0$, the sets $B(x, \epsilon) \cap Y$ and $B(x, \epsilon) \cap Y^c$ are both nonempty.

    - ($\implies$) Suppose that there exists an $\epsilon_0 > 0$ such that $B(x, \epsilon_0) \cap Y = \emptyset$. This implies that $B(x, \epsilon_0) \subseteq Y^c$ which means $x \in \mathrm{Int}(Y^c)$. Similarly suppose that $B(x, \epsilon_0) \cap Y^c = \emptyset$ Then $B(x, \epsilon_0) \subseteq Y$ so $x \in \mathrm{Int}(Y)$. In either case the forward implication is true.

    - ($\impliedby$) Suppose for all $\epsilon > 0$ we have $B(x, \epsilon) \not\subseteq Y$ and $B(x, \epsilon) \not\subseteq Y^c$. Then this means $x \notin \mathrm{Int}(Y)$ and $x \notin \mathrm{Int}(Y^c)$. However by the result, this means $x \in x \in \mathrm{Bd}(Y) = \mathrm{Bd}(Y^c)$.

A subset $Y$ in $(X, d)$ is __open__ if $Y = \mathrm{Int}(Y)$.

A subset $Y$ in $(X, d)$ is __closed__ if $Y^c$ is open.

__Lemma__: Let $(X, d)$ be a metric space, and let $Y \subseteq X$. Then $\mathrm{Int}(\mathrm{Int}(Y)) = \mathrm{Int}(Y)$,

??? success "Proof"

    - $\mathrm{Int}(\mathrm{Int}(Y)) \subseteq \mathrm{Int}(Y)$. Let $Z = \mathrm{Int}(Y)$. Then by definition $\mathrm{Int}(Z) \subseteq Z$, which proves the result.
    - $\mathrm{Int}(Y) \subseteq \mathrm{Int}(\mathrm{Int}(Y))$. Consider $x \in \mathrm{Int}(Y)$ then $\exists \epsilon_0 > 0$ such that $B(x, \epsilon_0) \subseteq Y$. Now we consider $y \in B(x, \epsilon_0)$. We argue that $y$ is an interior point of $Y$ by showing $B(y, \delta) \subseteq Y$. Choose $\delta = \epsilon - d(x, y) > 0$. Then for $z \in B(y, \delta)$ this implies $d(y, z) < \delta$. Then by the triangle inequality, $d(z, y) \leq d(z, y) + d(y, z) < \epsilon_0 - d(x, y) + d(y, x) = \epsilon_0$. So $z \in B(x, \epsilon_0)$ which means $B(y, \delta) \subseteq Y$. This implies $y \in \mathrm{Int}(Y)$, further implying $B(x, \epsilon) \subseteq \mathrm{Int}(Y)$ which in turn shows $x \in \mathrm{Int}(\mathrm{Int}(Y))$ which proves the result.

__Corollary__: For a subset $Y$ of a metric space $(X, d)$, the set $\mathrm{Int}(Y)$ is open.

The __closure__ of $Y$ is $\mathrm{Cl}(Y) = \mathrm{Int}(Y) \sqcup \mathrm{Bd}(Y)$ (disjoint union).

!!! example

    What is the closure of $\mathbb{R}$ in $\mathbb{R}$?

    We first argue that $\mathrm{Int}(\mathbb{R}) = \mathbb{R}$.

    - $\mathrm{Int}(\mathbb{R}) \subseteq \mathbb{R}$. Follows from the definition.
    - $\mathbb{R} \subseteq \mathrm{Int}(\mathbb{R})$. For all $x \in \mathbb{R}, B(x, 1) \subseteq \mathbb{R} \implies x \in \mathrm{Int}(\mathbb{R})$

    Hence since $\mathbb{R} = \mathrm{Int}(\mathbb{R}) \cup \mathrm{Bd}(\mathbb{R}) \cup \mathrm{Int}(\mathbb{R}^c) = \mathbb{R} \cup \emptyset \cup \emptyset$. So the closure of $\mathbb{R}$ is $\mathbb{R}$.

We say $Y$ is __dense__ if $\mathrm{CI}(Y) = X$.