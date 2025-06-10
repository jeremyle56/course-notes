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
            <object data="../../assets/lecture_notes/04062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
            <embed src="../../assets/04062025-lecture-slides.pdf.pdf" type="application/pdf"/>
            </object>
            </div>

    === "Lecture 2 - 05/06"

        1. The Schröder-Bernstein theorem is a powerful and practical result that allows us to avoid explicitly constructing bijections.
        2. A good demonstration of its usefulness is the equivalence between the intervals $[0, 1]$ and $[0, 1)$. Compare the bijection constructed in class with the simpler approach using $f(x) = x$ and $g(x) = x / 2$.
        3. Another strong example is the equivalence between $\mathbb{N}$ and $\mathbb{N} \times \mathbb{N}$. Using the Schröder-Bernstein theorem, we show $\mathbb{N}$ is smaller than $\mathbb{N} \times \mathbb{N}$ via the identity, and $\mathbb{N} \times \mathbb{N}$ is smaller than $\mathbb{N}$ using a mapping based on prime numbers.
        4. A set is called finite if it corresponds to the first $n$ natural numbers for some $n$; otherwise, it is infinite.
        5. Every infinite set is at least as large as $\mathbb{N}$. Consider whether the Axiom of choice is needed to prove this.
        6. Dedekind-finite and Dedekind-infinite are alternative definitions of finite and infinite sets; we showed these match the standard definitions.
        7. We classify sets as finite, countable infinite, or uncountable.
        8. All the examples we've seen so far have been either finite or countably infinite.
        9. The set of rational numbers is countably infinite.
        10. The first example of an uncountable set is the power set of $\mathbb{N}$.
        11. The interval [0, 1] is uncountable; it can be mapped to the power set of $\mathbb{N}$, or we can use Cantor’s diagonal argument to show this directly.
        12. The theorem on page 45 is a useful and practical tool for showing that a set is countable.
        13. We demonstrated how to use the theorem from page 45 (the countable union theorem) by showing that the set of all finite subsets of $\mathbb{N}$ is countable.

        ??? abstract "05/06 Lecture Slides"

            <div>
            <object data="../../assets/lecture_notes/05062025-lecture-slides.pdf" type="application/pdf" style="width: 100%; min-height: 100vh">
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

- __injective__ (or "one-to-one") - every element of $B$ is assigned to _at most_ one element of $A$. Formally:

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

## Comparison of Sets

We say that two sets $A$ and $B$ have the same __cardinality__ if there is a bijection $f: A \to B$; we then write $A \sim B$.

!!! example

    The set of integers $\mathbb{Z}$ has the same cardinality as the set of even integers $2\mathbb{Z}$. We can define the bijection $f : \mathbb{Z} \to 2\mathbb{Z}; f(n) = 2n$.

!!! example

    The empty set $\emptyset$ does not have the same cardinality as the set $\{0\}$. More generally, the sets $\{0, 1, 2, \dots, m\}$ and $\{0, 1, 2, \dots, n\}$, with $m \neq n$, do not have the same cardinality ("pigeonhole principle").

### Cantor's Theorem

Let $S$ be any set, and let $\mathcal{P}(S)$ be its power set. Then $S \nsim \mathcal{P}(S)$.

### Equivalence Relations

For any sets $A, B$ and $C$, we have:

- $A \sim A$ (reflexive)
- $A \sim B \implies B \sim A$ (symmetric)
- $A \sim B \text{ and } B \sim C \implies A \sim C$ (transitive)

Then we refer to $|A|$ as the "cardinality" of $A$ and use the following notation:

- $|A| = |B|$ if $A \sim B$.
- $|A| \leq |B|$ if there is an injective function $f : A \to B$.
- $|A| < |B|$ if $|A| \leq |B|$ and $|A| \neq |B|$.

### Schroeder-Bernstein Theorem

Let $A$ and $B$ be sets, and suppose that there exist injective functions $f: A \to B$ and $g: B \to A$. Then there exists a bijective function $h: A \to B$.

!!! example

    Show that $[0, 1]$ and $[0, 1)$ have the same cardinality.

    - $|A| \leq |B|$, then $f : A \to B$ injective. Define $f(x) = x$ then $A \subseteq B$.
    - $|B| \leq |A|$, then $g : B \to A$ injective. Define $S = \left\{\frac{1}{n} : n = 1, 2, 3, \dots \right\} \subseteq B$ and

        \[
            g(x) = \begin{cases}
                x &: x \in B \setminus S, \\
                \frac{1}{n + 1} &: x \in S, x = \frac{1}{n}
            \end{cases}
        \]

    Then by Schroeder-Bernstein there exists a bijective function $h: A \to B$.

!!! example

    Prove that $\mathbb{N}$ and $\mathbb{N} \times \mathbb{N}$ have the same cardinality.

    - $|\mathbb{N}| \leq |\mathbb{N} \times \mathbb{N}|$, define $f: \mathbb{N} \to \mathbb{N} \times \mathbb{N}; f(n) = (n, 0)$ for all $n \in \mathbb{N}$.
    - $|\mathbb{N} \times \mathbb{N}| \leq |\mathbb{N}|$, define $g: \mathbb{N} \times \mathbb{N} \to \mathbb{N}; g(m, n) = 2^m 3^n$.

    Then by Schroeder-Bernstein there is a bijection between $\mathbb{N}$ and $\mathbb{N} \times \mathbb{N}$ so $\mathbb{N} \sim (\mathbb{N} \times \mathbb{N})$.

## Finiteness

A set $S$ is finite if $|S| = |\{1, \dots, n\}|$, for some $n \in \mathbb{N}$. Otherwise $S$ is infinite.

### Dedekind-finiteness

A set $S$ is __Dedekind-infinite__ if there is a bijection from $S$ to a proper subset of itself. Otherwise $S$ is Dedekind-finite.

!!! example

    The set $\mathbb{N}$ is Dedekind-infinite with map $f: \mathbb{N} \to 2\mathbb{N}; f(n) = 2n$ which is a bijection.

## Countability

We say that a set $S$ is __countable__ if $|S| \leq |\mathbb{N}|$. Otherwise $S$ is __uncountable__. If $S$ is countable and infinite we say that $S$ is __countably infinite__.

!!! example

    The set $\mathbb{Q}$ is countable. We express each rational number as $\frac{a}{b}$ with $a, b \in \mathbb{Z}$ and send to $(a, b) \in \mathbb{Z} \times \mathbb{Z}$. This is an injection, and so we have

    \[
        |\mathbb{Q}| \leq |\mathbb{Z} \times \mathbb{Z}| = |\mathbb{N} \times \mathbb{N}| = |\mathbb{N}|,
    \]

    using the fact that $|\mathbb{Z}| = |\mathbb{N}|$.

!!! example

    The set $\mathcal{P}(\mathbb{N})$ is uncountable.

    By Cantor's Theorem, we have $|S| \neq |\mathcal{P}(S)|$. On the other hand, we can inject $S$ into $\mathcal{P}(S)$ by $x \mapsto \{x\}$. So $|\mathcal{P}(S)| > |S|$, and therefore in particular $|\mathcal{P}(\mathbb{N})| > |\mathbb{N}|$. Therefore $\mathcal{P}(\mathbb{N})$ is uncountable.

If $A$ is countably infinite and $g: A \to B$ is a bijection, then $B$ is countably infinite.

Every infinite set contains a countably infinite subset.

### Countable Union Theorem

Let $I$ be a countable set, and let $\{S_i\}_{i \in I}$ be a set of countable sets indexed by $I$. Then the union $\bigcup_{i \in I} S_i$ is countable.

??? success "Proof"

    Assume the hypothesis. Since $I$ is countable, there is an injection $f: I \to \mathbb{N}$. Since each $S_i$ is countable, we can choose an injection $f_i: S_i \to \mathbb{N}$ for each $i \in I$. We now define an injection

    \[
        g: \bigcup_{i \in I} S_i \to \mathbb{N} \times \mathbb{N}.
    \]

    For each element $x \in \bigcup_{i \in I} S_i$, choose an $i \in I$ such that $x \in S_i$. Then let $g(x) = (f(i), f_i(x))$. Convince yourself that is indeed an injection. Since $\mathbb{N} \times \mathbb{N}$ is countable, so is $\bigcup_{i \in I} S_i$. Hence, a countable union of countable sets is countable.