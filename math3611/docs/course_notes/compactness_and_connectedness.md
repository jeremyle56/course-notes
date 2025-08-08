# Compactness and Connectedness

??? note "Course Material"

    === "Lecture 16 - 31/07"

        ??? abstract "31/07 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/31072025-02-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            </object>
            </div>

## Introduction

A topological space $(X, \tau)$ is **compact** if for every $\{V_i\}_{i \in I} \subseteq \tau$ such that

\[X = \bigcup\_{i \in I} V_i,\]

there is a finite subset $\{i_1, \dots, i_n\} \subseteq I$ such that

\[X = \bigcup\_{i \in I}^n V_i\]

A subset $Y \subseteq X$ is compact if and only if it is compact in the subspace topology.

## Covers and Compactness

**Theorem:** The interval $[0, 1]$ is compact.

**Theorem:** Let $(X, \tau_X)$ and $(Y, \tau_Y)$ be compact topological spaces. Then $X \times Y$ is compact (in the product topology).

**Corollary:** Sets of the form $[a, b]^n \subseteq \mathbb{R}^n$ are compact (with the standard topology).

**Theorem (Heine-Borel):** A subset $X \subseteq \mathbb{R}^n$ is compact if and only if it is closed and bounded.

**Theorem (Bolzano-Weierstrass):** Every bounded sequence of real numbers has a convergent subsequence.

**Lemma:** Every sequence of real numbers has a monotone subsequence.

**Corollary:** Every bounded sequence in $\mathbb{R}^n$ has a convergent subsequence.

??? success "Proof"

    Prove follows by entry-wise application of Bolzano-Weierstrass.

## Sequentially Compactness

A topological space $(X, \tau)$ is called **sequentially compact** if every sequence in $X$ has a convergent subsequence. Similarly, a subset $Y \subseteq X$ is sequentially compact if it is sequentially compact in the subspace topology.

**Theorem:** Let $X$ be a subset of $\mathbb{R}^n$. The following are equivalent:

1. $X$ is compact
2. $X$ is sequentially compact
3. $X$ is closed and bounded

??? success "Proof"

    - $(1) \iff (3)$ by Heine Borel.
    - $(3) \implies (2)$ by Bolzano-Weierstrass.
    - $(2) \implies (3)$ ...

## Uniform Continuity

**Theorem:** Let $(X, \tau_X)$ and $(X, \tau_Y)$ be topological spaces. If $f: X \to Y$ is continuous and $X$ is compact, then $f(X) \subseteq Y$ is compact.

**Corollary (Min-max Theorem):** Let $f: [a, b] \to \mathbb{R}$ be a continuous function. Then $f$ attains maximum and minimum values.

Let $(X, d_X)$ and $(Y, d_Y)$ be metric spaces. A function $f: X \to Y$ is said to be **uniformly continuous** if $\forall \epsilon > 0, \exists \delta(\epsilon)$ such that $d_Y(f(x'), f(x)) < \epsilon$ whenever $d_X(x, x') < \delta$.

**Theorem:** Let $(X, d)$ be a compact metric space, and let $f: X \to \mathbb{R}$ be a continuous function. Then $f$ is uniformly continuous.

## Compactness in Metric Spaces

A metric space $(X, d)$ is said to be **totally bounded** if for *every* $\epsilon > 0$ there is a *finite* set $\{ x_1, \dots, x_n \} \subseteq X$ such that

\[X = \bigcup_{k=1}^n B(x_k, \epsilon).\]

Similarly, a subset of a metric space is totally bounded if it is totally bounded with respect to the subset metric.

**Theorem:** Let $(X, d)$ be a metric space. The following are equivalent:

1. $X$ is compact
2. $X$ is sequentially compact
3. $X$ is complete and totally bounded

## The Arzela-Ascoli Theorem

Let $(X, d_X)$ and $(Y, d_Y)$ be metric spaces. A subset $S \subseteq C(X, Y)$ is said to be:

1. **Pointwise equicontinuous** if

\[\forall x \in X, \epsilon > 0, \exists \delta(x, \epsilon), \text{ such that } \forall f \in S.\]

\[d_Y(f(x'), f(x)) < \epsilon \text{ whenever } d_X(x', x) < \delta.\]

2. **Uniformly equicontinuous** if

\[ \forall \epsilon > 0, \exists \delta(\epsilon), \text{ such that } \forall f \in S\]

\[d_Y(f(x'), f(x)) < \epsilon \text{ whenever } d_X(x', x) < \delta.\]

**Theorem:** let $(X, d_X)$ and $(Y, d_Y)$ be metric spaces, with $X$ compact. Then $S \subseteq C(X, Y)$ is pointwise equicontinuous if and only if it is uniformly equicontinuous.

**Theorem (Arzela-Ascoli):** A bounded subset of $(C[0, 1], \lVert \cdot \rVert_\infty)$ is totally bounded if and only if it is equicontinuous.

(More generally, $[0, 1]$ can be replace by any compact metric space).

**Corollary:** A subset of $(C[0, 1], \lVert \cdot \rVert_\infty)$ is compact if and only if it is closed, bounded and equicontinous.

**Corollary:** A uniformly bounded and equicontinuous sequence of functions on a closed interval $[a, b]$ has a uniformly convergent subsequence.

## The Weierstrass Approximation Theorem

**Theorem (Weierstrass Approximation Theorem):** Let $f$ be a continuous function on a closed, bounded interval $[a ,b]$. For any $\epsilon > 0$, there is a polynomial function $p(x)$ such that

\[\lVert f - p\rVert_\infty < \epsilon.\]

Consider a function $f \in C[0, 1]$. The $n^{th}$ **Bernstein polynomial** for $f$ is defined as

\[B_{f, n}(x) = \sum_{k = 0}^n f\left(\frac{k}{n}\right)\binom{n}{k} x^k(1 - x)^{n - k}, \quad x \in [0, 1].\]

Let $X$ and $Y$ be sets. A set $S$ of functions between $X$ and $Y$ is said to **separate points** if for every pair of distinct points $x, y \in X$, there is a function $f \in S$ such that $f(x) \neq f(y)$.

**Theorem (Urysohn's Lemma):** Let $X$ be a compact Hausdorff space. Then $C(X, \mathbb{R})$ separates points.

An **algebra** of functions is a vector space of functions with pointwise operations which is also closed under pointwise multiplication of functions. An algebra of functions is called **unital** if it contains the constant function 1.

**Theorem (Stone-Weierstrass Theorem):** Let $X$ be a compact Hausdorff space, and let $A \subseteq C(X, \mathbb{R})$ be a unital subalgebra. Then $A$ is dense with respect to $\lVert \cdot \rVert_\infty$ if and only if A separates points.

An algebra of complex-valued functions is called a **\*-algebra** if it is closed under pointwise complex conjugation.

**Theorem (Stone-Weierstrass Theorem - complex version):** Let $X$ be a compact Hausdorff space and let $A \subseteq C(X, \mathbb{C})$ be a unital \*-subalgebra. Then $A$ is dense with respect to $\lVert \cdot \rVert_\infty$ if and only if $A$ separates points.

**Theorem (Tychonoff's Theorem):** Let $\{(X_i, \tau_i)\}_{i \in I}$ be a collection of compact topological spaces. Then $\prod_{i \in I} X_i$ is compact in the product topology.

**Theorem:** Let $H$ be a Hilbert space. The closed unit ball in $H$ (i.e. $\{\mathbf{x} \in \mathbf{H} : \lVert \mathbf{x} \rVert \leq 1\}$) is compact in the weak topology.
