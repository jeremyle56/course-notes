# Cardinality

??? note "Course Material"

    === "Lecture 1 - 04/06"

        1. Russell’s paradox demonstrates that the naïve approach to set theory is unreliable.
        2. In the Zermelo–Fraenkel system, sets can only be constructed from existing sets using operations such as union, subset, power set, and Cartesian product.
        3. Functions and sequences are specific examples of Cartesian products.
        4. The Axiom of Choice is required to apply standard results, such as Zorn’s Lemma, but it is controversial because it leads to counterintuitive results, including the Banach–Tarski paradox.
        5. When mapping between sets, we test the maps for injectivity, surjectivity, or bijectivity.
        6. Two sets have the same cardinality if there exists a bijection between them.
        7. The sets $\mathbb{N}$ and $\mathbb{N} \times \mathbb{N}$ have the same cardinality, as shown by the diagonalisation map.
        8. A set and its power set do not have the same cardinality, as demonstrated by Cantor’s theorem.
        9. The relation 'set $A$ has the same or lesser cardinality than set $B$ ' has two equivalent definitions: there exists an injection $f: A \to B$ or a surjection $g: B \to A$.

        ??? abstract "04/06 Lecture Slides"

            <div>
            <object data="../../assets/04062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
            </object>
            </div>

    === "Lecture 2 - 05/06"

        1. The Schröder-Bernstein theorem is a powerful and practical result that allows us to avoid explicitly constructing bijections.
        2. A good demonstration of its usefulness is the equivalence between the intervals $0, 10, 1$ and $[0, 1)$. Compare the bijection constructed in class with the simpler approach using $f(x) = x$ and $g(x) = x / 2$.
        3. Another strong example is the equivalence between $\mathbb{N}$ and $\mathbb{N} \times \mathbb{N}$. Using the Schröder-Bernstein theorem, we show $\mathbb{N}$ is smaller than $\mathbb{N} \times \mathbb{N}$ via the identity, and $\mathbb{N} \times \mathbb{N}$ is smaller than $\mathbb{N}$ using a mapping based on prime numbers.
        4. A set is called finite if it corresponds to the first $n$ natural numbers for some $n$; otherwise, it is infinite.
        5. Every infinite set is at least as large as $\mathbb{N}$. Consider whether the Axiom of choice is needed to prove this.
        6. Dedekind-finite and Dedekind-infinite are alternative definitions of finite and infinite sets; we showed these match the standard definitions.
        7. We classify sets as finite, countable infinite, or uncountable.
        8. All the examples we've seen so far have been either finite or countably infinite.
        9. The set of rational numbers is countably infinite.
        10. The first example of an uncountable set is the power set of $\mathbb{N}$.
        11. The interval 0, 10, 1 is uncountable; it can be mapped to the power set of $\mathbb{N}$, or we can use Cantor’s diagonal argument to show this directly.
        12. The theorem on page 45 is a useful and practical tool for showing that a set is countable.
        13. We demonstrated how to use the theorem from page 45 (the countable union theorem) by showing that the set of all finite subsets of $\mathbb{N}$ is countable.

        ??? abstract "05/06 Lecture Slides"

            <div>
            <object data="../../assets/05062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            <embed src="../../assets/05062025-lecture-slides.pdf.pdf" type="application/pdf"/>
            </object>
            </div>

## Zermelo-Frankel Set Theory and the Axiom of Choice

Using the Zermelo-Frankel (ZF) axioms one can define numbers, develop arithmetic, and describe lots of other mathematical notions.

- Taking unions: If $S = \{T_i\}_{i \in I}$ is a set of sets, then the __union__: $\bigcup_{i \in I} T_i = \{x : \exists i \in I \text{ such that } x \in T_i\}$ is a set.

- __Subsets__ with a specified condition: If $S$ is a set and $\phi$ is a "condition" on elements, then $\{ x \in S: \phi(x) \}$ is a set.

- Power set: If $S$ is a set, then the __power set__ $\{T: T \subseteq S\}$ is a set.

The ZF axioms allow one to construct Cartesian products of indexed sets. If $A$ and $B$ are two sets, then the Cartesian product $A \times B$ is the set of all pairs, or "2-tuples", $(a, b)$ such that $a \in A$ and $b \in B$. Formally an $I$-tuple is a function from $I$ to $\bigcup_{i \in I} S_i$ such that

\[
f(i) \in S_i, \forall i \in I \text{ and } \prod_{i \in I} S_i = \{f : I \to \bigcup_{i \in I} S_i : f(i) \in S_i, \forall i \in I\}.
\]

!!! example
    If the index set $I$ is the set of natural numbers $\mathbb{N}$, and each of the $S_i$ is the set of real numbers, what is the Cartesian product $\prod_{i \in I} S_i$?

    \[
        \prod_{i \in \mathbb{N}} \mathbb{R} \text{ is the set of all real sequences.}
    \]

### Axiom of Choice

A Cartesian product of non-empty sets is non-empty (and thus one can "choose" an element of this Cartesian product). This defines a rule of select a number from an arbitrary non-empty set of real numbers.

## Functions

If $A$ and $B$ are sets, a function $f: A \to B$ is a "rule" which associates to each element of $A$ exactly one element of $B$.

A function $f: A \to B$ is called:

- __injective__ (or "1-1") - every element of $B$ is assigned to _at most_ one element of $A$. Formally:

    \[
        \forall x_1, x_2 \in A, f(x_1) = f(x_2) \implies x_1 = x_2.
    \]

- __surjective__ (or "onto") - every element of $B$ is assigned to _at least_ one element of $A$. Formally:

    \[
        \forall y \in B, \exists x \in A \text{ such that } f(x) = y.
    \]


- __bijective__ - every element of $B$ is assigned to _exactly_ one element of $A$ (= injective + surjective). Formally $

    \[
        \forall y \in B, \exists! x \in A \text{ such that } f(x) = y.
    \]