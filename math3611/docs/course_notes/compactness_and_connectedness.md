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

\[X = \bigcup_{i \in I} V_i,\]

there is a finite subset $\{i_1, \dots, i_n\} \subseteq I$ such that

\[X = \bigcup_{i \in I}^n V_i\]

A subset $Y \subseteq X$ is compact if and only if it is compact in the subspace topology.

**Theorem:** The interval $[0, 1]$ is compact.

**Theorem:** Let $(X, \tau_X)$ and $(Y, \tau_Y)$ be compact topological spaces. Then $X \times Y$ is compact (in the product topology).
