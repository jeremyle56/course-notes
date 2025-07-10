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

        ??? abstract "Boundary and Interior of $c_{00}$"

            <div>
                <object data="../../assets/lecture_notes/12062025-boundary_and_interior_of_c_00.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
                <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
                </object>
            </div>

    === "Lecture 5 - 18/06"

        1. The definition of convergence in a metric space can be equivalently stated using the concepts of neighbourhoods and open neighbourhoods.
        2. The collection of open sets in a metric space forms a topology.
        3. A topology satisfies three fundamental properties: it includes the empty set and the whole space; it is closed under arbitrary unions; and it is closed under finite intersections.
        4. The intersection of finitely many open sets is open, but this does not hold for infinite intersections.
        5. In the discrete metric, the topology coincides with the power set.
        6. Whether a set is open or closed depends on the surrounding metric space.
        7. The set of interior points of a set can be described as the union of all open subsets contained within it.
        8. A set is closed if and only if it contains all of its limit points.
        9. A function is continuous if it satisfies the epsilon–delta definition.
        10. A function is continuous if and only if the preimage of every open set is open.
        11. The topologies on $\mathbb{R}^n$ induced by the $d_p$ metrics (for $1 \leq p \leq \infty$) are all the same.
        12. The composition of continuous functions is continuous; the quickest proof uses the preimage characterisation of continuity.
        13. A bounded subset of a metric space can be defined in three different but equivalent ways.
        14. A Cauchy sequence is a powerful substitute for a convergent sequence, especially in spaces that are not complete.
        15. Every Cauchy sequence is bounded.

        ??? abstract "18/06 Lecture Slides"

            <div>
                <object data="../../assets/lecture_notes/18062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
                <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
                </object>
            </div>

    === "Lecture 6 - 19/06"

        1. Every convergent sequence is Cauchy.
        2. The metric spaces $(0, 1), \mathbb{Q}$ and $C[0, 1]$ with the $d_1$ metric are not complete.
        3. A complete metric space is one in which every Cauchy sequence converges to a point in that space.
        4. $\mathbb{R}$ (the set of real numbers) is complete.
        5. Any set with the discrete metric is complete.
        6. The set of $n$-tuples with any $d_p$ metric is complete.
        7. A subset of a complete metric space is complete (with the induced metric) if and only if it is closed.
        8. The metric space $C[0, 1]$ with $d_\infty$ metric is complete.
        9. This extends to the space $C(I, J)$ where $I$ and $J$ are subsets of $\mathbb{R}$, with $I$ closed and bounded, and $J$ closed.
        10. In every metric space, the set of all Cauchy sequences has a natural equivalence relation.
        11. This relation is an equivalence relation, meaning it is reflexive, symmetric, and transitive.
        12. The set of Cauchy sequences under this equivalence splits into equivalence classes.
        13. If one sequence in an equivalence class converges, then all sequences in that class also converge to the same limit.
        14. The set of all equivalence classes can be given a metric induced by the original metric space.

        ??? abstract "19/06 Lecture Slides"

            <div>
                <object data="../../assets/lecture_notes/19062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
                <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
                </object>
            </div>

    === "Lecture 7 - 25/06"

        1. The classes of equivalent Cauchy sequences can be given a metric that turns them into a metric space.
        2. The definition of this metric requires checking that it is well-defined; that is:

            a. the limit defining the metric is always converging, and
            b. it is independent of the choice of representatives from each equivalence class.

        3. A careful exposition of the result showing that the completion procedure yields a complete metric space—and that this space is unique up to isometry—can be found in Kolmogorov and Fomin, Section 7.4.
        4. The space of real numbers $\mathbb{R}$ is the completion of $\mathbb{Q}$ with the absolute value metric.
        5. The completion of $C[0, 1]$ with the $d_1$ metric is the space of equivalence classes of Lebesgue integrable functions.
        6. Many of the metric spaces we have encountered can also be viewed as normed spaces.
        7. A complete normed space is called a Banach space.
        8. The space $c_{00}$ is a normed space with the $\lVert \cdot \rVert_p$ norm but not Banach.
        9. The space $\ell^p$ is a Banach space with the $\lVert \cdot \rVert_p$ norm.
        10. The space $\ell^p$ is the completion of $c_{00}$.
        11. The proof that $\ell^p$ is a Banach space follows the same strategy as the proof that $C[0, 1]$ is Banach; we studied the argument in detail when we proved that $C[0, 1]$ is a complete metric space.
        12. Other spaces that fall into this category include $\mathbb{R}^n, \ell^\infty$ and $c_{0}$.

        ??? abstract "25/06 Lecture Slides"

            <div>
                <object data="../../assets/lecture_notes/25062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
                <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
                </object>
            </div>

    === "Lecture 8 - 26/06"

        1. Some normed spaces can be defined via inner product spaces.
        2. The norm defined via an inner product is indeed a norm; that is, it satisfies the triangle inequality.
        3. The key to proving the triangle inequality is the Cauchy–Schwarz inequality.
        4. This inequality is proved using a neat trick within the setting of inner product spaces.
        5. A complete inner product space is called a Hilbert space.
        6. $\mathbb{R}^n$, $\mathbb{C}^n$ and $\ell^2$ are examples of inner product spaces (and hence Hilbert spaces).
        7. The inner product in $\ell^2$ (and hence its status as a Hilbert space) requires verifying that the defining series always converges.
        8. $\ell^1$ is an inner product space but not a Hilbert space.
        9. A contraction is a special class of map that can be used to demonstrate the existence of solutions.
        10. Contractions are continuous.
        11. Recursive sequences defined via a contraction are Cauchy, and hence converge in complete metric spaces.
        12. Contraction Mapping Theorem: A contraction always have a unique fixed point in a complete metric space.
        13. We can use contractions to prove the existence of solutions to first-order ordinary differential equations (ODEs).
        15. This result is known as the Picard-Lindelöf Theorem.
        16. The key idea is to rewrite the ODE as an integral equation and consider the corresponding map.
        17. This map can be turned into a contraction if the metric space $C(I, J)$ is chosen carefully.
        18. The Picard–Lindelöf Theorem explains how to choose the intervals $I$ and $J$ to ensure that a contraction is obtained.

        ??? abstract "26/06 Lecture Slides"

            <div>
                <object data="../../assets/lecture_notes/26062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
                <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
                </object>
            </div>

    === "Lecture 9 - 02/07"

        1. The Picard–Lindelöf Theorem has two versions of sufficient conditions.
        2. The conditions on page 109 help prove the theorem by showing the integral operator is a contraction, but are hard to apply in practice.
        3. A simpler version uses the boundedness of the function $gg$ and its partial derivative with respect to $yy$.
        4. The link between the two versions is the concept of Lipschitz functions.
        5. Lipschitz functions lie between continuous and differentiable functions:

            - Every continuously differentiable function with bounded derivative is Lipschitz (by MVT).
            - Some continuous functions (e.g. $x^{1/3}$) are not Lipschitz.
            - Some Lipschitz functions (e.g. $|x|$) are not differentiable.

        6. For Picard–Lindelöf, the Lipschitz condition applies to gg with respect to yy; this reduces to boundedness of the yy-partial derivative.

        ??? abstract "02/07 Lecture Slides"

            <div>
                <object data="../../assets/lecture_notes/02072025-01-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
                <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
                </object>
            </div>

Recall the definition of a limit $\lim_{x \to a} f(x) = b$ means that "for any number $\epsilon > 0$, there is a number $\delta(\epsilon)$ such that $|f(x) - b| < \epsilon$ whenever $|x - a| < \delta$".

## What is a metric space?

A **metric space** is a pair $(X, d)$, where $X$ is a (non-empty) set and $d: X \times X \to [0, \infty)$ is a function, such that the following conditions hold for all $x, y, z \in X$:

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

**Theorem:** A sequence in a metric space can have at most one limit.

<!-- !!! example

    For metric spaces $X$ and $Y$, a function $f: X \to Y$ is said to be __sequentially continuous__ if for every convergent sequence $\{ x_0 \}_{n = 0}^\infty \subseteq X$ with limit $x$, the sequences $\{ f(x_n) \}_{n = 0}^\infty$ converges to $f(x)$ (in $Y$) -->

## Topology of Metric Spaces

For a point $x$ in a metric space $(X, d)$ and a number $\epsilon > 0$, define the (open) **$\epsilon$-ball**

\[
B(x, \epsilon) = \{ y \in X : d(y, x) < \epsilon \}
\]

!!! example

    - For $X = \mathbb{R}^2, d = d_1(\mathbf{x}, \mathbf{y}) = |x_1 - y_1| + |x_2 - y_2|$ then $B(\mathbf{0}, 1) = \{ \mathbf{x} \in \mathbb{R}^2 : |x_1| + |x_2| < 1 \}$.
    - For $X = \mathbb{R}^2, d = d_2$ then $B(\mathbf{0}, 1) = \{ \mathbf{x} \in \mathbb{R}^2 : |x_1|^2 + |x_2|^2  < 1 \}$.
    - For $X = \mathbb{R}, d = |\cdot|$-value then $B(a, \epsilon) = \{ x \in \mathbb{R} : |x - a| < \epsilon \}$.

Let $(X, d)$ be a metric space, and consider $Y \subseteq X$. Define the **interior**

\[
\mathrm{Int}(Y) = \{ y \in Y: \exists \epsilon > 0 \text{ such that } B(y, \epsilon) \subseteq Y \}
\]

Define the **boundary**

\[
\mathrm{Bd}(Y) = X \setminus (\mathrm{Int}(Y) \cup \mathrm{Int}(Y^c)).
\]

Then we can write $X = \mathrm{Int}(Y) \cup \mathrm{Bd}(Y) \cup \mathrm{Int}(Y^c)$.

!!! example

    Show that $x \in \mathrm{Bd}(Y)$ if and only if $\forall \epsilon > 0$, the sets $B(x, \epsilon) \cap Y$ and $B(x, \epsilon) \cap Y^c$ are both nonempty.

    - ($\implies$) Suppose that there exists an $\epsilon_0 > 0$ such that $B(x, \epsilon_0) \cap Y = \emptyset$. This implies that $B(x, \epsilon_0) \subseteq Y^c$ which means $x \in \mathrm{Int}(Y^c)$. Similarly suppose that $B(x, \epsilon_0) \cap Y^c = \emptyset$ Then $B(x, \epsilon_0) \subseteq Y$ so $x \in \mathrm{Int}(Y)$. In either case the forward implication is true.

    - ($\impliedby$) Suppose for all $\epsilon > 0$ we have $B(x, \epsilon) \not\subseteq Y$ and $B(x, \epsilon) \not\subseteq Y^c$. Then this means $x \notin \mathrm{Int}(Y)$ and $x \notin \mathrm{Int}(Y^c)$. However by the result, this means $x \in x \in \mathrm{Bd}(Y) = \mathrm{Bd}(Y^c)$.

A subset $Y$ in $(X, d)$ is **open** if $Y = \mathrm{Int}(Y)$.

A subset $Y$ in $(X, d)$ is **closed** if $Y^c$ is open.

!!! warning

    Is $[0, 1]$ open? Is $[0, 1]$ closed?

    - If $Y = [0, 1] \subseteq \mathbb{R} = X$. Then $Y$ is closed but not open.
    - If $Y = [0, 1] \subseteq [0, 1] = X$. Then $Y$ is both closed and open.

**Lemma**: Let $(X, d)$ be a metric space, and let $Y \subseteq X$. Then $\mathrm{Int}(\mathrm{Int}(Y)) = \mathrm{Int}(Y)$,

??? success "Proof"

    - $\mathrm{Int}(\mathrm{Int}(Y)) \subseteq \mathrm{Int}(Y)$. Let $Z = \mathrm{Int}(Y)$. Then by definition $\mathrm{Int}(Z) \subseteq Z$, which proves the result.
    - $\mathrm{Int}(Y) \subseteq \mathrm{Int}(\mathrm{Int}(Y))$. Consider $x \in \mathrm{Int}(Y)$ then $\exists \epsilon_0 > 0$ such that $B(x, \epsilon_0) \subseteq Y$. Now we consider $y \in B(x, \epsilon_0)$. We argue that $y$ is an interior point of $Y$ by showing $B(y, \delta) \subseteq Y$. Choose $\delta = \epsilon - d(x, y) > 0$. Then for $z \in B(y, \delta)$ this implies $d(y, z) < \delta$. Then by the triangle inequality, $d(z, y) \leq d(z, y) + d(y, z) < \epsilon_0 - d(x, y) + d(y, x) = \epsilon_0$. So $z \in B(x, \epsilon_0)$ which means $B(y, \delta) \subseteq Y$. This implies $y \in \mathrm{Int}(Y)$, further implying $B(x, \epsilon) \subseteq \mathrm{Int}(Y)$ which in turn shows $x \in \mathrm{Int}(\mathrm{Int}(Y))$ which proves the result.

**Corollary**: For a subset $Y$ of a metric space $(X, d)$, the set $\mathrm{Int}(Y)$ is open.

The **closure** of $Y$ is $\mathrm{Cl}(Y) = \mathrm{Int}(Y) \sqcup \mathrm{Bd}(Y)$ (disjoint union).

!!! example

    What is the closure of $\mathbb{R}$ in $\mathbb{R}$?

    We first argue that $\mathrm{Int}(\mathbb{R}) = \mathbb{R}$.

    - $\mathrm{Int}(\mathbb{R}) \subseteq \mathbb{R}$. Follows from the definition.
    - $\mathbb{R} \subseteq \mathrm{Int}(\mathbb{R})$. For all $x \in \mathbb{R}, B(x, 1) \subseteq \mathbb{R} \implies x \in \mathrm{Int}(\mathbb{R})$

    Hence since $\mathbb{R} = \mathrm{Int}(\mathbb{R}) \cup \mathrm{Bd}(\mathbb{R}) \cup \mathrm{Int}(\mathbb{R}^c) = \mathbb{R} \cup \emptyset \cup \emptyset$. So the closure of $\mathbb{R}$ is $\mathbb{R}$.

We say $Y$ is **dense** if $\mathrm{CI}(Y) = X$.

Let $(X, d)$ be a metric space. An **open neighbourhood** of a point $x \in X$ is an open set $V \subseteq X$ such that $x \in V$. A **neighbourhood** of $x$ is a set $U \subseteq X$ such that there is an open neighbourhood $V$ of $x$ with $V \subseteq U$.

The set of open sets in a metric space $X$ is called the **topology** of $X$. We will denote the topology by $\mathcal{O}(X)$.

Let $(X, d)$ be a metric space. The topology has the following properties:

1. $\emptyset, X, \in \mathcal{O}(X)$
2. If $\{V_i\}_{i \in I} \subseteq \mathcal{O}(X)$, then $\bigcup_{i \in I} V_i \in \mathcal{O}(X)$. ("a union of open sets is open")
3. If $V_1, V_2 \in \mathcal{O}(X)$, then $V_1 \cap V_2 \in \mathcal{O}(X)$. ("a finite intersection of open sets is open")

**Theorem**: Let $(X, d_X)$ and $(Y, d_Y)$ be metric spaces. A function $f: X \to Y$ is continuous if and only if

\[
\text{For every } V \in \mathcal{O}(Y), \text{ we have } f^{-1}(V) \in \mathcal{O}(X).
\]

(In words: "the pre-image of every open set is open.")

**Theorem**: Let $(X, d_X), (Y, d_Y), (Z, d_Z)$ be metric spaces, and suppose $f: X \to Y$ and $g: Y \to Z$ are continuous functions. Then the composition $g \circ f: X \to Z$ is continuous.

## Boundedness

**Lemma**: Let $(X, d)$ be a metric space, and let $\emptyset \neq Y \subseteq X$. The following are equivalent:

1. For every $x \in X$, there is an $R(x) > 0$ such that $Y \subseteq B(x, R)$.
2. There exists $y \in Y$ and $R$ such that $Y \subseteq B(y, R)$
3. There is an $R > 0$ such that for any $y_1, y_2 \in Y$, we have $d(y_1, y_2) < R$.

A subset of a metric space $Y \subseteq X$ satisfying these equivalent conditions is called **bounded**. (If $Y = X$ we say that metric space is bounded.)

!!! example

    Let $X = C[0, 1]$, and consider the sequence of functions $\{f_n\}_{n = 1,2, \dots}.

    \[
        f_n(x) = \begin{cases}
        n - n^2 x & 0 \leq x \leq \frac{1}{n},
        0 & \frac{1}{n} < x \leq 1.
        \end{cases}
    \]

    Is this sequence bounded?

    Take $x = 0$, then $d_\infty(f_n, x) = \sup_{x \in [0, 1]} |f_n(x)| = n < R(0)$. So the first statement fails, hence the sequence is not bounded.

## Completeness

A sequence $\{ x_n \}_{n = 0}^\infty$ in a metric space $(X, d)$ is a **Cauchy sequence** if for every $\epsilon > 0$, there is a $K(\epsilon)$ such that $d(x_m, x_n) < \epsilon$ whenever $m ,n > K(\epsilon)$.

Every Cauchy sequence is bounded.

Every convergent sequence is a Cauchy sequence.

A metric space $(X, d)$ is called **complete** if every Cauchy sequence in $X$ converges to a point in $X$.

!!! example

    The following are listed below without proof but you should prove them yourself to confirm these results:

    - $(0, 1)$ and $\mathbb{Q}$, with the metrics inherited from $\mathbb{R}$, are not complete.
    - $C[0, 1]$ with the metric $d_1$ is not complete.
    - A discrete metric space is complete.
    - $\mathbb{R}$ (with the usual metric$ is complete).
    - $(\mathbb{R}^2, d_2) is complete. Similarly, $(\mathbb{R}^n, d_p)$ is complete for any $n$ and any $p \in [1, \infty]$.

**Theorem**: Let $(X, d)$ be a complete metric space, and let $Y \subseteq X$. Then $Y$ is complete (with the subset metric) if and only if $Y$ is closed.

**Theorem**: The metric space $(C[0, 1], d_\infty)$ is complete.

??? success "Outline of Proof for Cauchy convergent to a function"

    Given a Cauchy sequence $\{ f_n \}_{n = 0}^\infty$ in $(C[0, 1], d_\infty)$, we want to show that this sequence converges to some function $f$.

    There are three steps:

    1. Show that for each specific $x \in [0, 1]$, the sequence $\{f_n\}_{n = 0}^\infty$ is a Cauchy sequence in $\mathbb{R}$ (and therefore converges to a number by completeness of $\mathbb{R}$.)
    2. Define $f(x)$ to be the limit of $\{ f_n \}_{n = 0}^\infty$ for each $x$. Show that $f(x)$ is continuous (and therefore belong to $C[0, 1]$).
    3. Show that $\{ f_n \}_{n = 0}^\infty$ converges to $f(x)$ in the $d_\infty$ metric.

Two Cauchy sequences $\{ a_n \}_{n = 1}^\infty$ and $\{ b_n \}_{n = 1}^\infty$ in a metric space $(X, d)$ are said to be **equivalent** if the sequence $\{ d(a_n, b_n) \}_{n = 1}^\infty$ converges to $0$ (in $\mathbb{R}$).

Two Cauchy sequences in a complete metric space are equivalent if and only if they have the same limit.

**Definition**: Let $(X, d)$ be a metric space. Let $\bar{X}$ be the set of **equivalence classes** of Cauchy sequences in $X$. We write $[\{a_n\}]$ for the equivalence class of the sequence $\{a_n\}$.

Define $\bar{d}: \bar{X} \times \bar{X} \to [0, \infty)$ as follows:

\[
\bar{d}([\{a_n\}], [\{b_n\}]) = \lim\_{n \to \infty} d(a_n, b_n)
\]

(Note that this definition assume that the limit exists, and does not depend on which representatives of the equivalence classes are taken.)

**Theorem**: Let $(X, d)$ be a metric space.

1. The completion $(\bar{X}, \bar{d})$ (as defined above) is a complete metric space.
2. Consider the function $i: X \to \bar{X}$ which sends $x \in X$ to the equivalence class of the constant sequence $\{ x\}$. Then $i$ is an \textbf{isometry}. (i.e. $\bar{d}(i(x), i(y)) = d(x,y), \forall x,y \in X$), and $i(X)$ is dense in $\bar{X}$.
3. The completion is unique in the following sense. Suppose $Y$ is another complete metric space and $j: X \to Y$ is an isometry such that $j(X)$ is dense in $Y$. Then there is a bijective isometry $f: Y \to \bar{X}$ such that $f \circ j = i$.

## Normed Spaces

Let $V$ be a vector space (over $k = \mathbb{R}$ or $k = \mathbb{C}$). A **norm** on $V$ is a function

\[
\lVert\cdot\rVert: V \to [0, \infty), \quad \mathbf{x} \mapsto \lVert\mathbf{x}\rVert,
\]

satisfying the following conditions for all $\mathbf{x}, \mathbf{y} \in V$ and $\lambda \in k$

1. $\lVert\mathbf{x}\rVert = 0 \implies \mathbf{x} = \mathbf{0}$
2. $\lVert\lambda\mathbf{x\rVert} = |\lambda| \cdot \lVert\mathbf{x}\rVert$
3. $\lVert\mathbf{x + \mathbf{y}}\rVert \leq \lVert\mathbf{x}\rVert + \lVert\mathbf{y}\rVert$.

**Theorem**: Let $(V, \lVert\cdot\rVert)$ be a normed vector space. Then $(V, d_{\lVert\cdot\rVert})$ is a metric space, where $d_{\lVert\cdot\rVert}$ is defined by

\[
d\_{\lVert\cdot\rVert}(\mathbf{x}, \mathbf{y}) = \lVert\mathbf{x} - \mathbf{y}\rVert, \forall \mathbf{x}, \mathbf{y} \in V.
\]

A complete normed space is called a **Banach** space.

For $p \in [1, \infty)$, let

\[
\ell^p = \{\{x*n\}*{n = 1}^\infty \subset \mathbb{R} : \sum\_{n = 1}^\infty |x_n|^p < \infty\},
\]

which is a vector space with pointwise operations. Define the norm

\[
\lVert \{x*n\}*{n=1}^\infty \rVert*p = \left(\sum*{n = 1}^\infty |x_n|^p)^{\frac{1}{p}} \right).
\]

**Theorem**: The normed vector space $(\ell^p, \lVert \cdot \rVert_p)$ is a Banach space.

??? success "Outline of Proof"

    1. Show that for each coordinate $k \in \mathbb{N}$, we get a Cauchy sequence of numbers.
    2. Show that the pointwise limit is a sequence in $\ell^p$.
    3. Show that the sequence (of sequences) converges to the pointwise limit in $d_p$.

An **inner product space** is a vector space $V$ (over $k = \mathbb{R}$ or $k = \mathbb{C}$), together with a function

\[
\langle \cdot, \cdot \rangle: V \times V \to k, \quad (\mathbf{x}, \mathbf{y}) \mapsto \langle \mathbf{x}, \mathbf{y} \rangle,
\]

such that for any $\mathbf{x}, \mathbf{y}, \mathbf{z} \in V$ and $\lambda \in k$, we have

1. $\langle \mathbf{x}, \mathbb{x} \rangle > 0$ for $\mathbf{x} \neq \mathbf{0}$
2. $\langle \mathbf{x}, \mathbf{y} \rangle = \overline{\langle\mathbf{y}, \mathbf{x}\rangle}$
3. $\langle \mathbf{x} + \lambda\mathbf{y}, \mathbf{z} \rangle = \langle \mathbf{x}, \mathbf{z} \rangle + \lambda \langle \mathbf{y}, \mathbf{z} \rangle$.

<!-- !!! example

    Show that if $(V, \langle \cdot, \cdot \rangle)$ is an inner product space, then the function

    \[
        \lVert \mathbf{x} \rVert = \langle \mathbf{x}, \mathbf{x} \rangle^\frac{1}{2}
    \]

    gives a norm (and hence a metric) on $V$. (Hint: Use the Cauchy-Schwartz inequality: $|\langle u, v \rangle| \leq \lVert u \rVert \lVert v \rVert$)

    \[
        \lVert u + v \rVert^2 = \langle u + v, u + v \rangle = \langle u, u \rangle + \langle v, v \rangle + \langle u, v \rangle + \langle v, u \rangle = \lVert u \rVert^2 + \lVert v \rVert^2 + 2 \mathrm{Re}(z),
    \]

    where $z = \langle u, v \rangle$. Then

    \begin{align*}
        &\leq \lVert u \rVert^2 + \lVert v \rVert^2 + 2 |\langle u, v \rangle| \\
        &\leq \lVert u \rVert^2 + \lVert v \rVert^2 + 2\lVert u \rVert \lVert v \rVert \\
        &= (\lVert u \rVert + \lVert v \rVert)^2
    \end{align*} -->

A complete inner product space is called a **Hilbert space**.

!!! example

    1. $\mathbb{R}^n$ is a real Hilbert space with the dot product
    2. $\mathbb{C}^n$ is a complex Hilbert space with the inner product

        \[
            \langle (x_1, \dots, x_n), (y_1, \dots, y_n) \rangle = \sum_{k = 1}^n x_k \overline{y_k}.
        \]

## Contraction Mappings

A **contraction** on a metric space $(X, d)$ is a function $f: X \to X$ such that there is a number $c < 1$ for which

\[
d(f(x), f(y)) \leq c \cdot d(x, y), \forall x, y \in X.
\]

**Contraction Mapping Theorem**: Let $(X, d)$ be a complete metric space, and let $f: X \to X$ be a contraction. Then $f$ has a unique **fixed point** $x = f(x)$.

Moreover, for any $x_0 \in X$, the recursively defined sequence $x_{n + 1} = f(x_n)$ converges to the fixed point $x$.

<!-- **Picard-Lindelof Theorem**: Consider the differential equation

\[
y' = \cos(xy).
\]

Does this have a solution?

??? succcess "Solution"

    Integrate both sides gives, $y(x) = \int_a^x \cos(ty(t)) \, dt + b$. Then we have $T(y)(x) = \int_0^x \cos(ty(t)) \, dt + b$.
    This means $y(x) \to T(y)(x)

    X = C(I, J) continious functions $f: I \to J$

    P-L theorem chooses I and J such that $T$ is a contraction. -->

Let $X \subseteq \mathbb{R}$. A function $f: X \to \mathbb{R}$ is called **Lipschitz continuous** if there is a $K > 0$ such that

\[
|f(x) - f(y)| \leq K|x - y|, \forall x, y \in X.
\]

The number $K$ is then called a **Lipschitz constant** for $f$.

If $X \subseteq \mathbb{R}^2$, then $f: X \to \mathbb{R}$ is **Lipschitz continuous in the second variable** if there is a $K > 0$ such that

\[
|f(x, y_1) - f(x, y_2)| \leq K \cdot |y_1 - y_2|, \forall (x, y_1), (x, y_2) \in X.
\]

**Theorem (Picard–Lindelöf):** Let $g$ be a continous function on a neighbourhood of $(a, b) \in \mathbb{R}^2$ which is Lipschitz continuous in the second variable. Then there is an interval around $a$ on which the differential equation

\[
y' = g(x, y), \quad y(a) = b
\]

has a unique solution.
