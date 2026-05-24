# Topological Spaces

??? note "Course Material"

    === "Lecture 11 - 16/07"

        1. A **topological space** is a set equipped with a *topology* - a family of subsets satisfying the topology axioms.
        2. Every **metric space** is a topological space.
        3. There exist topological spaces that are **not** metric spaces.
        4. A subset of a topological space can be given the **subspace topology**.
        5. The **interior** of a set $Y$, denoted $\mathrm{Int}(Y)$ is open in the topological space.
        6. A topological space is the most general setting in which **convergence of sequences** can be defined.
        7. **Continuous maps** between topological spaces are defined using the **preimage** formulation.
        8. The preimage definition is equivalent to the traditional definition in topological spaces.
        9. Some topological spaces are **Hausdorff**.
        10. The defining feature of a Hausdorff space is the **uniqueness of limits**.
        11. There are topological spaces where limits are unique, yet the space is **not Hausdorff**.

        ??? abstract "16/07 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/16072025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            </object>
            </div>

    === "Lecture 12 - 17/07"

        1. In $\mathbb{R}$ with the standard topology, every open set is a countable union of disjoint open intervals.
        2. This property does **not** hold in $\mathbb{R}^2$.
        3. To describe topologies using simpler families of subsets, we use the concepts of a **base** for a topology and a **local base** for neighbourhoods.
        4. The topology itself forms a base, but it is often possible to reduce the base to a **smaller family**.
        5. In a metric space, the family of **open balls with rational radii** forms a base.
        6. Any family of subsets satisfying conditions (1) and (2) on page 41 forms a **base** for a topology.
        7. Definitions of **continuity** and **convergence** can be stated in terms of a base.
        8. A base can be further reduced to a **subbase**; any family of subsets can serve as a subbase for a topology.
        9. The resulting topology is the **smallest topology** containing the given family of subsets.
        10. **Convergence of sequences** can be tested using only the elements of a subbase.

        ??? abstract "17/07 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/17072025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            </object>
            </div>

    === "Lecture 13 - 23/07"

        ??? abstract "23/07 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/23072025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            </object>
            </div>

    === "Lecture 14 - 24/07"

        ??? abstract "24/07 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/24072025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            </object>
            </div>

    === "Lecture 15 - 30/07"

        ??? abstract "30/07 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/30072025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            </object>
            </div>

    === "Lecture 15 - 30/07"

        ??? abstract "30/07 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/30072025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            </object>
            </div>

    === "Lecture 16 - 31/07"

        ??? abstract "31/07 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/31072025-01-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            </object>
            </div>

## Introduction and Definitions

A topological space is a set $X$ together with a set of subsets $\tau = \mathcal{O}(X) \subseteq \mathcal{P}(X)$ satisfying

1. $\emptyset, X \in \mathcal{O}(X)$
2. If ${V_i}_{i \in I} \subseteq \mathcal{O}(X)$, then $\bigcup_{i \in I} V_i \in \mathcal{O}(X)$.
3. If $V_1, V_2 \in =\mathcal{O}(X)$, then $V_1 \cap V_2 \in \mathcal{O}(X)$.

!!! example "Common Examples of Topologies"

    1. Let $(X, d)$ be a metric space. Then we have already seen the metric topology $\tau_d$.
    2. Let $X$ be any set. The **coarse topology** is $\tau = \{\emptyset, X\}$.
    3. Let $X$ be any set. The **discrete topology** is $\tau = \mathcal{P}(X)$.
    4. Let $X$ be any set. The **cofinite topology** is $\tau = \{Y \subseteq X : Y^C \text{ is finite}\} \cup \{\emptyset\}$.
    5. Let $X$ be any set. The **cocountable topology** is $\tau = \{Y \subseteq X: Y^C \text{ is countable}\} \cup \{\emptyset\}$.

Let $(X, \tau)$ be a topological space, and let $Y \subseteq X$. The **subspace topology** (also called **relative topology**) is $\tau|_Y = \{V \cap Y : V \in \tau\}$.

Let $(X, \tau)$ be a topological space. A subset $Y \subseteq X$ is closed if $Y^C$ is open.

Let $(X, \tau)$ be a topological space.

1. Let $x \in X$ be a point. An **open neighbourhood** of $x$ is a set $V \in \tau$ such that $x \in V$. A **neighbourhood** of $x$ is any set containing an open neighbourhood of $x$. We will denote the collection of neighbourhoods of $x$ by $\mathrm{Nbhd}(x)$.
2. Let $Y \subseteq X$ be a subset. The **interior** of $Y$ is

\[
\mathrm{Int}(Y) = \{y \in E: \exists V_y \in \mathrm{Nbhd}(y) \text{ such that } V_y \subseteq Y\}.
\]

Let $(X, \tau)$ be a topological space. For any subset $Y \subseteq X$, the interior $\mathrm{Int}(Y)$ is an open set.

Let $(X, \tau)$ be a topological space, and let $Y \subset X$.

1. The **boundary** is $\mathrm{Bd}(Y) = X \setminus (\mathrm{Int}(Y) \sqcup \mathrm{Int}(Y^C))$
2. The **closure** is $\mathrm{cl}(Y) = \mathrm{Int}(Y) \cup \mathrm{Bd}(Y)$.

## Convergence in Topological Spaces

Let $(X, \tau)$ be a topological space. A sequence $\{x_n\}_{n = 1}^\infty \subseteq X$ **converges** to $x \in X$ if for every $V \in \mathrm{Nbhd}(x)$, there is a $K(V) \in \mathbb{N}$ such that $x_n \in V$ when $n \geq K$.

Let $(X, \tau_X)$ and $(Y, \tau_Y)$ be topological spaces. A function $f: X \to Y$ is **continuous** if for every $V \in \tau_Y$, we have $f^{-1}(V) \in \tau_X$.

Let $(X, \tau_X), (Y, \tau_Y)$ and $(Z, \tau_Z)$ be topological spaces. If $f: X \to Y$ and $g: Y \to Z$ are continuous functions, then $(g \circ f): X \to Z$ is also continuous.

A topological space $X$ has the **Hausdorff property** if for every pair of distinct points $x, y \in X$, there are neighbourhoods $V(x, y) \in \mathrm{Nbhd}(x)$ and $U(x, y) \in \mathrm{Nbhd}(y)$ such that $V(x, y) \cap U(x, y) = \emptyset$.

A sequence in a Hausdorff space has at most one limit.

## Bases for Topologies

Let $(X, \tau)$ be a topological space.

1. A **base** for $\tau$ is a subset $\mathcal{B} \subset \tau$ such that every $V \in \tau$ can be expressed as a union of elements of $\mathcal{B}$:

    \[V = \bigcup_{i \in I} V_i, \text{ where } V_i \in \mathcal{B}, \forall i \in I \]

2. A **local base** for $\tau$ at a point $x \in X$ is a collection $\mathcal{LB}_x \subseteq \tau$ of open neighbourhoods of $x$ such that if $U$ is any neighbourhood of $x$, there is a $V \in \mathcal{LB}_x$ such that $V \subseteq U$.

**Theorem:** Let $X$ be a set, and let $\mathcal{B} \subseteq \mathcal{P}(X)$ be a collection of subsets. Then

\[\tau = \{ V \subseteq X: V \text{ is a union of sets in } \mathcal{B} \} \]

is a topology iff the following conditions hold:

1. $\bigcup_{V \in \mathcal{B}} V = X$ ("$\mathcal{B}$ covers $X$")
2. for every $V_1$ and $V_2$ in $\mathcal{B}$ and every $x \in V_1 \cap V_2$, there is $V \in \mathcal{B}$ such that $x \in V \subseteq V_1 \cap V_2$.

Let $X$ be a set, and $S \subseteq \mathcal{P}(X)$ be a collection of subsets. Define $\mathcal{B}$ to be the set of all **finite** intersections of sets in $S$.

\[\mathcal{B} = \{V_1 \cup \cdots \cup V_n : V_k \in S, k = 1, \dots, n \}.\]

(We allow the empty intersection $X$). Then $\mathcal{B}$ satisfies the conditions for a base in the previous theorem, so

\[\tau(S) = \{V \subseteq X, V \text{ is a union of sets in } \mathcal{B}\}\]

is a topology. We call $S$ a **subbase** for $\tau(S)$, and say that $\tau$ is generated by $S$.

## Pointwise and Weak Convergence

Let $X$ be a set and let $Y = F(X, \mathbb{R})$. For each $x \in X, y \in \mathbb{R}$, and $\epsilon > 0$, define

\[V_{x, y, \epsilon} = \{g \in Y : |g(x) - y| < \epsilon \}.\]

Then let

\[S = \{V_{x, y, \epsilon} \}_{x \in X, y \in \mathbb{R}, \epsilon > 0}.\]

Finally, define the topology of pointwise convergence to be $\tau_{pt} = \tau(S)$, the topology generated by the subbase $S$.

**Theorem:** A sequence of functions $f_n : X \to \mathbb{R}$ converges pointwise to $f$ if and only if $f_n \to f$ in the topology $\tau_{pt}$.

Let $\mathbf{H}$ be a Hilbert space, such as $\mathbb{R}^n$ or $\ell^2$. We say that a sequence of vectors $\{ x_n \}_{n=1}^\infty$ converges **weakly** to a vector $\mathbf{x} \in \mathbf{H}$ if for every vector $\mathbf{y} \in \mathbf{H}$, we have

\[\langle \mathbf{x}_n, \mathbf{y} \rangle \to \langle \mathbf{x}, \mathbf{y} \rangle.\]

Let $(a, b)$ be an open interval in $\mathbb{R}$. A sequence of functions is said to converge compactly if it converges uniformly on every closed subinterval $[c, d] \subseteq (a, b)$.

## Countability

A topological space $(X, \tau)$ is said to be:

1. **First countable** if every point in $X$ has a countable local base for $\tau$.
2. **Second countable** if $X$ has a countable base for $\tau$.

A topological space is **separable** if it contains a countable dense subset.

Let $(X, \tau)$ be a topological space. A local base $\{V_n\}_{n \in \mathbb{N}}$ at a point $x$ is called **nested** if $V_n \subseteq C_m, \forall n \geq m$.

Let $(X, \tau)$ be a first countable topological space. Then a subset $Y  \subseteq X$ is closed if and only if for every sequence in $Y$ which converges (in $X$), the limit is in $Y$.

## Nets

A **directed set** is a set $\Lambda$, together with a binary relation $\leq$ satisfying, for all $i, j, k \in Lambda$

1. $i \leq i$
2. $i \leq j$ and $j \leq k \implies i \leq k$
3. $\exists m \in \Lambda$ such that $i, j \leq m$.

A **net** is a function from a directed set $(\Lambda, \leq)$ to a set $X$. As for sequences, we'll use the notation $\{x_\lambda\}_{\lambda \in \Lambda}$.

Let $(X, \tau)$ be a topological space. A net $\{x_\lambda\}_{\lambda \in \Lambda}$ converges to a point $x \in X$ if for every neighbourhood $V$ of $x$, there is an $\alpha(V) \in \Lambda$ such that $x_\lambda \in V$ when $\lambda \geq \alpha$.

**Theorem:** Let $(X, \tau)$ be a topological space. The $Y \subseteq X$ is closed if and only if $Y$ contains the limits of all of its convergent nets.

## Comparison of Topologies

Suppose $\tau$ and $\sigma$ are two topologies on a set $X$ such that $\tau \subseteq \sigma$. Then we say that $\tau$ is **coarser** and $\sigma$ is **finer**.

## Homeomorphisms

Let $(X, \tau_X)$ and $(Y, \tau_Y)$ be topological spaces. A bijection $f: X \to Y$ is a called a **homeomorphism** if both $f$ and $f^{-1}$ are continuous. We say that $X$ and $Y$ are **homeomorphic** if there exists a homomorphism $f: X \to Y$.

Two metric $(X, d_X)$ and $(Y, d_Y)$ are said to be **isometric** if there is a bijection $f: X \to Y$ such that

\[_Y(f(x_1), f(x_2)) = d_X(x_1, x_2), \forall x_1, x_2 \in X.\]

Two metric spaces $(X, d_X)$ and $(Y, d_Y)$ are said to be **equivalent** if there is a bijection $f: X \to Y$ and constants $k, K > 0$ such that

\[k \cdot d_X(x_1, x_2) \leq d_Y(f(x_1), f(x_2)) \leq K \cdot d_X(x_1, x_2), \forall x_1, x_2 \in X.\]

Two normed spaces $(X, \lVert \cdot \rVert_X)$ and $(Y, \lVert \cdot \rVert_Y)$ are said to be **equivalent** if there is a bijection $f: X \to Y$ and constants $k, K > 0$ such that

\[k \cdot \lVert \mathbf{x} \rVert_X \leq \lVert f(\mathbf{x}) \rVert_Y \leq K \cdot \lVert \mathbf{x} \rVert_X, \forall x_1, x_2 \in X.\]

### Homeomorphism Invariants

A topological space $(X, \tau)$ is **connected** if it is not the union of two disjoint nonempty open subsets. A subset $Y \subseteq X$ is connected if it is connected in the subspace topology.

**Theorem:** The interval $[0, 1]$ is connected.

**Theorem:** Let $(X, \tau_X)$ and $(Y, \tau_Y)$ be topological spaces, and suppose $f: X \to Y$ is a continuous function. If $X$ is connected, then so is $f(X)$ (as a subset of $Y$).

**Lemma:** Let $(X, \tau)$ be a topological space, and suppose that $\{W_i\}_{i \in I}$ are connected subsets such that $\bigcap_{i \in I} W_i \neq \emptyset$. Then $\bigcap_{i \in I} W_i$ is connected.

The equivalence classes of $X$ under $~^{ct}$ are called the **connected components** of $X$.

A topological space $(X, \tau)$ is **path-connected** if for every pair of points $x, y \in X$, there is a continuous function $f: [0, 1] \to X$ such that $f(0) = x$ and $f(1) = y$. A subset $Y \subseteq X$ is path-connected if it is path-connected in the subspace topology.

**Theorem:** If a topological space is path-connected, then it is connected.

Let $(X, \tau_X)$ and $(Y, \tau_Y)$ be topological spaces. The product topology on $X \times Y$ is the topology generated by the base

\[\{U \times V\}_{U \in \tau_X, V \in \tau_Y}.\]

Let $\{(X_i, \tau_i)\}_{i \in I}$ be a collection of topological spaces. The **box topology** $\prod_{i \in I} X_i$ is the topology with base

\[\mathcal{B} = \left\{\prod_{i \in I} U_i : U_i \in \tau_i, \forall i \in I \right\}\]

Let $\{(X_i, \tau_i)\}_{i \in I}$ be a set of topological spaces. The **product topology** on $\prod_{i \in I} X_i$ is the topology generated by the base

\[\left\{ \prod_{i \in I} U_i : U_i \in \tau_i, \forall i \in I \text{ and } U_i = X_i \text{ for all but finitely many } i \in I \right\}\]
