---
aliases: [0.1  The language of set theory]
created: 2023-10-01T14:51:47-07:00
modified: 2023-10-14T18:34:53-07:00
tags: 
---
# 0.1  The language of set theory
 - Page 2:
 -  Much of analysis relies on the language of set theory, but one may also use the words family and collection synonymously with the word set.
 > [!def Empty set]
 > The empty set, the set with no elements, is denoted as $\emptyset$.

 >[!def power set]
>
 >The family of all subsets, the **power set of set $X$** is often denoted $$
  \mathcal{P}(X) = \{E: E \subset X\} $$

 > [!def union and intersection of sets]
>
 > If $\mathcal{E}$ is a family of sets, we can form the **union and intersection** of its members:
>  $$\begin{aligned} & \bigcup_{E \in \mathcal{E}} E=\{x: x \in E \text { for some } E \in \mathcal{E}\}, \\ & \bigcap_{E \in \mathcal{E}} E=\{x: x \in E \text { for all } E \in \mathcal{E}\} . \end{aligned}$$

 > [!def disjoint sets]
 > If $E_\alpha \cap E_\beta=\varnothing$ whenever $\alpha \neq \beta$, the sets $E_\alpha$ are called **disjoint**.

- When considering families of sets indexed by $\mathbb{N}$, our usual notation will be $\left\{E_n\right\}_{n=1}^{\infty} \text { or }\left\{E_n\right\}_1^{\infty}$ and likewise for unions and intersections. In this situation, the notions of limit superior and limit inferior are sometimes useful:

> [!def limit superior / inferior]
> $$\lim \sup E_n=\bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} E_n, \quad \liminf E_n=\bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} E_n$$

 The reader may verify that

 $\begin{aligned} \lim \sup E_n & =\left\{x: x \in E_n \text { for infinitely many } n\right\} \\ \liminf E_n & =\left\{x: x \in E_n \text { for all but finitely many } n\right\} \end{aligned}$

- Page 3
> [!def differences of sets]
> If $E$ and $F$ are sets, we denote their difference by $E \backslash F$ :
> $E \backslash F=\{x: x \in E \text { and } x \notin F\},$
and their symmetric difference by
> $E \triangle F$ :$E \Delta F=(E \backslash F) \cup(F \backslash E)$

> [!def complement of a set]
>
> When it is clearly understood that all sets in question are subsets of a fixed set $X$, we define the complement $E^c$ of a set $E$ (in $X$ ): $E^c=X \backslash E$


> [!lemma deMorgan's laws]
> $$\left(\bigcup_{\alpha \in A} E_\alpha\right)^c=\bigcap_{\alpha \in A} E_\alpha^c, \quad\left(\bigcap_{\alpha \in A} E_\alpha\right)^c=\bigcup_{\alpha \in A} E_\alpha^c$$

> [!def cartesian product of two sets / relations]
>  If $X$ and $Y$ are sets, their Cartesian product $X \times Y$ is the set of all ordered pairs $(x, y)$ such that $x \in X$ and $y \in Y$. A relation from $X$ to $Y$ is a subset of $X \times Y$. (If $Y=X$, we speak of a relation on $X$.) If $R$ is a relation from $X$ to $Y$, we shall sometimes write $x R y$ to mean that $(x, y) \in R$.

The most important types of relations are the following:

 - equivalence relations
 - orderings
 - mappings

> [!def Equivalence relations]
>  An **equivalence relation** on $X$ is a relation $R$ on $X$ such that
>
> $$  \begin{aligned} & x R x \text { for all } x \in X, \\ & x R y \text { iff } y R x, \\ & x R z \text { whenever } x R y \text { and } y R z \text { for some } y . \end{aligned}  $$
> The equivalence class of an element $x$ is $\{y \in X: x R y\} . X$ is the disjoint union of these equivalence classes.

> [!def Mappings]
>  A **mapping** $f: X \rightarrow Y$ is a relation $R$ from $X$ to $Y$ with the property that for every $x \in X$ there is a unique $y \in Y$ such that $x R y$, in which case we write $y=f(x)$. Mappings are sometimes called maps or functions; we shall generally reserve the latter name for the case when $Y$ is $\mathbb{C}$ or some subset thereof.

> [!def composition of mappings / inverse image of a mapping]
> If $f: X \rightarrow Y$ and $g: Y \rightarrow Z$ are mappings, we denote by **$g \circ f$ their composition**:
> $$ g \circ f: X \rightarrow Z, \quad g \circ f(x)=g(f(x)) . $$
> If $D \subset X$ and $E \subset Y$, we define the **image of $D$ and the inverse image of $E$ under a mapping $f: X \rightarrow Y$** by
> $$ f(D)=\{f(x): x \in D\}, \quad f^{-1}(E)=\{x: f(x) \in E\} . $$

Page 4

It is easily verified that the map $f^{-1}: \mathcal{P}(Y) \rightarrow \mathcal{P}(X)$ defined by the second formula commutes with union, intersections, and complements:

$$ \begin{gathered} f^{-1}\left(\bigcup_{\alpha \in A} E_\alpha\right)=\bigcup_{\alpha \in A} f^{-1}\left(E_\alpha\right), \quad f^{-1}\left(\bigcap_{\alpha \in A} E_\alpha\right)=\bigcap_{\alpha \in A} f^{-1}\left(E_\alpha\right), \\ f^{-1}\left(E^c\right)=\left(f^{-1}(E)\right)^c . \end{gathered} $$

(The direct image mapping $f: \mathcal{P}(X) \rightarrow \mathcal{P}(Y)$ commutes with unions, but in general not with intersections or complements. This is an important fact for defining mappings in topological spaces)

> [!def domain / range of a function]
> If $f: X \rightarrow Y$ is a mapping, $X$ is called the domain of $f$ and $f(X)$ is called the range of $f$.

> [!def injectivity / surjectivity / bijectivity of functions]
> $f$ is said to be injective if $f\left(x_1\right)=f\left(x_2\right)$ only when $x_1=x_2$, surjective if $f(X)=Y$, and bijective if it is both injective and surjective. If $f$ is bijective, it has an inverse $f^{-1}: Y \rightarrow X$ such that $f^{-1} \circ f$ and $f \circ f^{-1}$ are the identity mappings on $X$ and $Y$, respectively.

> [!Notation restriction of a function to a subset of a domain]
> If $A \subset X$, we denote by $f \mid A$ the restriction of $f$ to $A$ : $$ (f \mid A): A \rightarrow Y, \quad(f \mid A)(x)=f(x) \text { for } x \in A . $$

> [!def sequence / subsequence]
> A sequence in a set $X$ is a mapping from $\mathbb{N}$ into $X$. (We also use the term finite sequence to mean a map from $\{1, \ldots, n\}$ into $X$ where $n \in \mathbb{N}$.) If $f: \mathbb{N} \rightarrow X$ is a sequence and $g: \mathbb{N} \rightarrow \mathbb{N}$ satisfies $g(n)<g(m)$ whenever $n<m$, the composition $f \circ g$ is called a subsequence of $f$.

one can define the Cartesian product of $n$ sets in terms of ordered $n$-tuples. However, this definition becomes awkward for infinite families of sets, so the following approach is used instead.

> [!def cartesian product of indexed family of sets]
> If $\left\{X_\alpha\right\}_{\alpha \in A}$ is an indexed family of sets, their Cartesian product $\prod_{\alpha \in A} X_\alpha$ is the set of all maps $f: A \rightarrow \bigcup_{\alpha \in A} X_\alpha$ such that $f(\alpha) \in X_\alpha$ for every $\alpha \in A$.

>[!def coordinates / coordinate maps]
If $X=\prod_{\alpha \in A} X_\alpha$ and $\alpha \in A$, we define the $\alpha$-th projection or coordinate map $\pi_\alpha: X \rightarrow X_\alpha$ by $\pi_\alpha(f)=f(\alpha)$. We also frequently write $x$ and $x_\alpha$ instead of $f$ and $f(\alpha)$ and call $x_\alpha$ the $\alpha$-th coordinate of $x$.
If the sets $X_\alpha$ are all equal to some fixed set $Y$, we denote $\prod_{\alpha \in A} X_\alpha$ by $Y^A$ :
$Y^A=$ the set of all mappings from $A$ to $Y$.

# 0.2 Orderings

Page 5

>[!def partial ordering / linear ordering]
>A partial ordering on a nonempty set $X$ is a relation $R$ on $X$ with the following properties:
>- if $x R y$ and $y R z$, then $x R z$;
>- if $x R y$ and $y R x$, then $x=y$
>- $x R x$ for all $x$.
>
>If $R$ also satisfies
>- if $x, y \in X$, then either $x R y$ or $y R x$, then $R$ is called a linear (or total) ordering.

We observe that a partial ordering on $X$ naturally induces a partial ordering on every nonempty subset of $X$.

> [!def order isomorphic]
> Two partially ordered sets $X$ and $Y$ are said to be order isomorphic if there is a bijection $f: X \rightarrow Y$ such that $x_1 \leq x_2$ iff $f\left(x_1\right) \leq f\left(x_2\right)$.

> [!def maximal/minimal element of a set. upper / lower bound for a subset]
> If $X$ is partially ordered by $\leq$, **a maximal (resp. minimal) element** of $X$ is an element $x \in X$ such that the only $y \in X$ satisfying $x \leq y$ (resp. $x \geq y$ ) is $x$ itself. Maximal and minimal elements may or may not exist, and they need not be unique unless the ordering is linear. **If $E \subset X$, an upper (resp. lower) bound for $E$** is an element $x \in X$ such that $y \leq x$ (resp. $x \leq y)$ for all $y \in E$.

> [!def well ordering / well ordered]
 If $X$ is linearly ordered by $\leq$ and every nonempty subset of $X$ has a (necessarily unique) minimal element, $X$ is said to be **well ordered** by $\leq$, and (in defiance of the laws of grammar) $\leq$ is called a **well ordering** on $X$. For example, $\mathbb{N}$ is well ordered by its natural ordering.

> [!lemma 0.1 The Hausdorff Maximal Principle.]
>  Every partially ordered set has a maximal linearly ordered subset.

In more detail, this means that if $X$ is partially ordered by $\leq$, there is a set $E \subset X$ that is linearly ordered by $\leq$, such that no subset of $X$ that properly includes $E$ is linearly ordered by $\leq$. Another version of this principle is the following:

> [!lemma 0.2 Zorn's Lemma]
> If $X$ is a partially ordered set and every linearly ordered subset of $X$ has an upper bound, then $X$ has a maximal element.

(Clearly??? [Q::Uhh how does hausdorff maximal principal imply zorn's lemma? and also the contrapositive]) the Hausdorff maximal principle implies Zorn's lemma: An upper bound for a maximal linearly ordered subset of $X$ is a maximal element of $X$. It is also not difficult to see that Zorn's lemma implies the Hausdorff maximal principle. (Apply Zorn's lemma to the collection of linearly ordered subsets of $X$, which is partially ordered by inclusion.)

> [!lemma 0.3 The Well Ordering Principle]
>Every nonempty set $X$ can be well ordered.

Page 6

> [!lemma 0.4 The Axiom of Choice.]
> If $\left\{X_\alpha\right\}_{\alpha \in A}$ is a nonempty collection of nonempty sets, then $\prod_{\alpha \in A} X_\alpha$ is nonempty.

Proof. Let $X=\bigcup_{\alpha \in A} X_\alpha$. Pick a well ordering on $X$ and, for $\alpha \in A$, let $f(\alpha)$ be the minimal element of $X_\alpha$. Then $f \in \prod_{\alpha \in A} X_\alpha$.

[Q::How is there a proof? Isn't the axiom of choice an axiom?? It seems to be because of the hausdorf maximal principal]

> [!Corollary 0.5.]
If $\left\{X_\alpha\right\}_{\alpha \in A}$ is a disjoint collection of nonempty sets, there is a set $Y \subset \bigcup_{\alpha \in A} X_\alpha$ such that $Y \cap X_\alpha$ contains precisely one element for each $\alpha \in A$.

Proof. Take $Y=f(A)$ where $f \in \prod_{\alpha \in A} X_\alpha$.

We have deduced the axiom of choice from the Hausdorff maximal principle; in fact, it can be shown that the two are logically equivalent. [Q:: How does axiom of choice imply the hausdorff maximal principal]

# 0.3 Cardinality
> [!def Relating cardinality of two sets]
> If $X$ and $Y$ are nonempty sets, we define the expressions

$$

 \operatorname{card}(X) \leq \operatorname{card}(Y), \quad \operatorname{card}(X)=\operatorname{card}(Y), \quad \operatorname{card}(X) \geq \operatorname{card}(Y)

$$

to mean that there exists $f: X \rightarrow Y$ which is injective, bijective, or surjective, respectively. We also define

$$

 \operatorname{card}(X)<\operatorname{card}(Y), \quad \operatorname{card}(X)>\operatorname{card}(Y)

$$

to mean that there is an injection but no bijection, or a surjection but no bijection, from $X$ to $Y$. Observe that we attach no meaning to the expression " $\operatorname{card}(X)$ " when it stands alone; there are various ways of doing so, but they are irrelevant for our purposes (except when $X$ is finite - see below). These relationships can be extended to the empty set by declaring that

$$

 \operatorname{card}(\varnothing)<\operatorname{card}(X) \text { and } \operatorname{card}(X)>\operatorname{card}(\varnothing) \text { for all } X \neq \varnothing

$$

Page 7

> [!Proposition 0.6]
> $\operatorname{card}(X) \leq \operatorname{card}(Y)$ iff $\operatorname{card}(Y) \geq \operatorname{card}(X)$.

> [!Proposition 0.7]
> For any sets $X$ and $Y$, either $\operatorname{card}(X) \leq \operatorname{card}(Y)$ or $\operatorname{card}(Y) \leq$ $\operatorname{card}(X)$

> [!Theorem 0.8 Schröder-Bernstein]
> If $\operatorname{card}(X) \leq \operatorname{card}(Y)$ and $\operatorname{card}(Y) \leq$ $\operatorname{card}(X)$ then $\operatorname{card}(X)=\operatorname{card}(Y)$.

> [!Proposition 0.9]
> For any set $X, \operatorname{card}(X)<\operatorname{card}(\mathcal{P}(X))$.

[Q:: Why is \operatorname{card}(X) \leq \operatorname{card}(\mathcal{P}(X))? Not understanding the converse of the proof.]

> [!def countable set, countably infinite set]
> A set $X$ is called countable (or denumerable) if $\operatorname{card}(X) \leq \operatorname{card}(\mathbb{N})$. In particular, all finite sets are countable, and for these it is convenient to interpret "card $(X)$ " as the number of elements in $X$ :
>
> $$
>  \operatorname{card}(X)=n \text { iff } \operatorname{card}(X)=\operatorname{card}(\{1, \ldots, n\}) .  
> $$
>
> If $X$ is countable but not finite, we say that $X$ is countably infinite.

Page 8

> [!Proposition 0.10]
a. If $X$ and $Y$ are countable, so is $X \times Y$.
b. If $A$ is countable and $X_\alpha$ is countable for every $\alpha \in A$, then $\bigcup_{\alpha \in A} X_\alpha$ is countable.
c. If $X$ is countably infinite, then $\operatorname{card}(X)=\operatorname{card}(\mathbb{N})$.

> [!Corollary 0.11]
> $\mathbb{Z}$ and $\mathbb{Q}$ are countable.

> [!def cardinality of the continuum]
> A set $X$ is said to have the **cardinality of the continuum** if $\operatorname{card}(X)=\operatorname{card}(\mathbb{R})$. We shall use the letter $\mathfrak{c}$ as an abbreviation for $\operatorname{card}(\mathbb{R})$ :
>
> $$
> \operatorname{card}(X)=c \text { iff } \operatorname{card}(X)=\operatorname{card}(\mathbb{R}) .
> $$

> [!Proposition 0.12]
> $\operatorname{card}(\mathcal{P}(\mathbb{N}))=\mathfrak{c}$.
- Consider the base 2 expansion of any natural number then since $\operatorname{card}(\mathcal{P}(\mathbb{Z}) = \operatorname{card}(\mathcal{P}(\mathbb{N})$, then the result follows from Schroder-bernstein thrm


> [!Corollary 0.13 ]
> If $\operatorname{card}(X) \geq c$, then $X$ is uncountable.

Proof. Apply Proposition 0.9.

The converse of this corollary is the so-called continuum hypothesis, whose validity is one of the famous undecidable problems of set theory; see $\S 0.7$.

Page 9

> [!Proposition 0.14]
a. If $\operatorname{card}(X) \leq \mathfrak{c}$ and $\operatorname{card}(Y) \leq \mathfrak{c}$, then $\operatorname{card}(X \times Y) \leq \mathfrak{c}$.
b. If $\operatorname{card}(A) \leq \mathrm{c}$ and $\operatorname{card}\left(X_\alpha\right) \leq \mathrm{c}$ for all $\alpha \in A$, then $\operatorname{card}\left(\cup_{\alpha \in A} X_\alpha\right) \leq \mathfrak{c}$.

# 0.4 More about well ordered sets

Said that these are mostly optional set theoretic facts used in only some exercises.

> [!def infimum / supremum of a set]
Let $X$ be a well ordered set. If $A \subset X$ is nonempty, $A$ has a minimal element, which is its maximal lower bound or infimum; we shall denote it by inf $A$. If $A$ is bounded above, it also has a minimal upper bound or supremum, denoted by sup $A$.

Page 10

# 0.5 The extended real number system
> [!def extended real number system]
It is frequently useful to adjoin two extra points $\infty(=+\infty)$ and $-\infty$ to $\mathbb{R}$ to form the extended real number system $\overline{\mathbb{R}}=\mathbb{R} \cup\{-\infty, \infty\}$, and to extend the usual ordering on $\mathbb{R}$ by declaring that $-\infty<x<\infty$ for all $x \in \mathbb{R}$.

The completeness of $\mathbb{R}$ can then be stated as follows: Every subset $A$ of $\mathbb{R}$ has a least upper bound, or supremum, and a greatest lower bound, or infimum, which are denoted by $\sup A$ and $\inf A$. If $A=\left\{a_1, \ldots a_n\right\}$, we also write

$$

\max \left(a_1, \ldots, a_n\right)=\sup A, \quad \min \left(a_1, \ldots, a_n\right)=\inf A

$$

Page 11

> [!def limit superior / inferior of a sequence]
The limit superior and limit inferior for a sequence $\{x_n\} \in \overline{\mathbb{R}}$ is defined as

$$

 \limsup x_n=\inf _{k \geq 1}\left(\sup _{n \geq k} x_n\right), \quad \liminf x_n=\sup _{k \geq 1}\left(\inf _{n \geq k} x_n\right) .

$$

> [!lemma]
every sequence $\left\{x_n\right\}$ in $\overline{\mathbb{R}}$ has a limit superior and a limit inferior

proof: from completeness of $\overline{\mathbb{R}}$

>[!lemma]
The sequence $\left\{x_n\right\}$ converges (in $\mathbb{R}$ ) iff the limit superior and limit inferior are equal (and finite), in which case its limit is their common value.

> [!def limit superior / inferior for functions]
>
> One can also define limsup and lim inf for functions $f: \mathbb{R} \rightarrow \overline{\mathbb{R}}$, for instance:

$$
 \limsup _{x \rightarrow a} f(x)=\inf _{\delta>0}\left(\sup _{0<|x-a|<\delta} f(x)\right).
$$

The arithmetical operations on $\mathbb{R}$ can be partially extended to $\overline{\mathbb{R}}$ :

$$

 \begin{gathered} x \pm \infty= \pm \infty(x \in \mathbb{R}), \quad \infty+\infty=\infty, \quad-\infty-\infty=-\infty, \\ x \cdot( \pm \infty)= \pm \infty(x>0), \quad x \cdot( \pm \infty)=\mp \infty(x<0) . \end{gathered}

$$

> [!def uncountable sums of non-negative functions]
We will occasionally encounter uncountable sums of nonnegative numbers. If $X$ is an arbitrary set and $f: X \rightarrow[0, \infty]$, we define $\sum_{x \in X} f(x)$ to be the supremum of its finite partial sums:

$$

 $\sum_{x \in X} f(x)=\sup \left\{\sum_{x \in F} f(x): F \subset X, F\right.$ finite $\}$.

$$

Later we shall recognize this as the integral of $f$ with respect to counting measure on $X$.

>[!Proposition 0.20]
> Given $f: X \rightarrow[0, \infty]$, let $A=\{x: f(x)>0\}$. If $A$ is uncountable, then $\sum_{x \in X} f(x)=\infty$. If $A$ is countably infinite, then $\sum_{x \in X} f(x)=$ $\sum_1^{\infty} f(g(n))$ where $g: \mathbb{N} \rightarrow A$ is any bijection and the sum on the right is an ordinary infinite series.

Page 12

> [!def increasing / decreasing / monotone real function]
If $X \subset \overline{\mathbb{R}}$  and $f: X \rightarrow \overline{\mathbb{R}}, f$  is called **increasing** if $f(x) \leq f(y)$ whenever $x \leq y$ and **strictly increasing** if $f(x)<f(y)$ whenever $x<y$; similarly for **decreasing**. A function that is either only increasing or only decreasing is called **monotone**.

If $f: \mathbb{R} \rightarrow \mathbb{R}$ is an increasing function, then $f$ has rightand left-hand limits at each point:

$$

f(a+)=\lim _{x \backslash a} f(x)=\inf _{x>a} f(x), \quad f(a-)=\lim _{x / a} f(x)=\sup _{x<a} f(x) .

$$

Moreover, the limiting values $f(\infty)=\sup _{a \in \mathbb{R}} f(x)$ and $f(-\infty)=\inf _{a \in \mathbb{R}} f(x)$ exist (possibly equal to $\pm \infty$ ).

> [!def left/right continuous function]
$f$ is called right continuous if $f(a)=f(a+)$ for all $a \in \mathbb{R}$ and left continuous if $f(a)=f(a-)$ for all $a \in \mathbb{R}$.

For points $x$ in $\mathbb{R}$ or $\mathbb{C},|x|$ denotes the ordinary absolute value or modulus of $x$, $|a+i b|=\sqrt{a^2+b^2}$. For points $x$ in $\mathbb{R}^n$ or $\mathbb{C}^n,|x|$ denotes the Euclidean norm:

$$

|x|=\left[\sum_1^n\left|x_j\right|^2\right]^{1 / 2} .

$$

> [!def open set in \mathbb{R}]
We recall that a set $U \subset \mathbb{R}$ is open if, for every $x \in U, U$ includes an interval centered at $x$.

> [!Proposition 0.21]
Every open set in $\mathbb{R}$ is a countable disjoint union of open intervals.

# 0.6 Metric spaces

Page 13

> [!def metric on a set, metric space]
> A metric on a set $X$ is a function $\rho: X \times X \rightarrow[0, \infty)$ such that
> - $\rho(x, y)=0$ iff $x=y$;
> - $\rho(x, y)=\rho(y, x)$ for all $x, y \in X$;
> - $\rho(x, z) \leq \rho(x, y)+\rho(y, z)$ for all $x, y, z \in X$.
>
>(Intuitively, $\rho(x, y)$ is to be interpreted as the distance from $x$ to $y$.) A set equipped with a metric is called a **metric space**.

Some examples:

i. The Euclidean distance $\rho(x, y)=|x-y|$ is a metric on $\mathbb{R}^n$.

ii. $\rho_1(f, g)=\int_0^1|f(x)-g(x)| d x$ and $\rho_{\infty}(f, g)=\sup _{0 \leq x \leq 1}|f(x)-g(x)|$ are metrics on the space of continuous functions on $[0,1]$.

iii. If $\rho$ is a metric on $X$ and $A \subset X$, then $\rho \mid(A \times A)$ is a metric on $A$.

iv. the product metric

> [!def product metric]
> If $\left(X_1, \rho_1\right)$ and $\left(X_2, \rho_2\right)$ are metric spaces, the product metric $\rho$ on $X_1 \times X_2$ is given by
>
> $$ \rho\left(\left(x_1, x_2\right),\left(y_1, y_2\right)\right)=\max \left(\rho_1\left(x_1, y_1\right), \rho_2\left(x_2, y_2\right)\right) .  $$

Other metrics are sometimes used on $X_1 \times X_2$, for instance,

$$

 \rho_1\left(x_1, y_1\right)+\rho_2\left(x_2, y_2\right) \text { or }\left[\rho_1\left(x_1, y_1\right)^2+\rho_2\left(x_2, y_2\right)^2\right]^{1 / 2} \text {. }

$$

These, however, are equivalent to the product metric in the sense that we shall define at the end of this section.

> [!open ball in a metric space]
>
> Let $(X, \rho)$ be a metric space. If $x \in X$ and $r>0$, the (open) ball of radius $r$ about $x$ is
$$ B(r, x)=\{y \in X: \rho(x, y)<r\} \text {. }  $$ $$ $$

> [!def open / closed sets in a metric space]
A set $E \subset X$ is **open** if for every $x \in E$ there exists $r>0$ such that $B(r, x) \subset E$, and **closed** if its complement is open.

For example, every ball $B(r, x)$ is open, for if $y \in B(r, x)$ and $\rho(x, y)=s$ then $B(r-s, y) \subset B(r, x)$. Also, $X$ and $\varnothing$ are both open and closed. Clearly the union of any family of open sets is open, and hence the intersection of any family of closed sets is closed. Also, the intersection (resp. union) of any finite family of open (resp. closed) sets is open (resp. closed). Indeed, if $U_1, \ldots U_n$ are open and $x \in \bigcap_1^n U_j$, for each $j$ there exists $r_j>0$ such that $B\left(r_j, x\right) \subset U_j$, and then $B(r, x) \subset \bigcap_1^n U_j$ where $r=\min \left(r_1, \ldots, r_n\right)$, so $\bigcap_1^n U_j$ is open.

> [!def interior of a set]
If $E \subset X$, the union of all open sets $U \subset E$ is the largest open set contained in $E$; it is called the interior of $E$ and is denoted by $E^{\circ}$.

> [!def closure of a set]
Likewise, the intersection of all closed sets $F \supset E$ is the smallest closed set containing $E$; it is called the closure of $E$ and is denoted by $\bar{E}$ .

> [!def dense / nowhere-dense set / separable set]
$E$ is said to be dense in $X$ if $\bar{E}=X$, and nowhere dense if $\bar{E}$ has empty interior. $X$ is called separable if it has a countable dense subset.

(For example, $\mathbb{Q}^n$ is a countable dense subset of $\mathbb{R}^n$.) A sequence $\left\{x_n\right\}$ in $X$ converges to $x \in X$ (symbolically: $x_n \rightarrow x$ or $\lim x_n=x$ ) if $\lim _{n \rightarrow \infty} \rho\left(x_n, x\right)=0.$

Page 14

> [!Proposition 0.22]
> If $X$ is a metric space, $E \subset X$, and $x \in X$, the following are equivalent:
> a. $x \in \bar{E}$.
> b. $B(r, x) \cap E \neq \varnothing$ for all $r>0$.
> c. There is a sequence $\left\{x_n\right\}$ in $E$ that converges to $x$.

> [!def continuous function in a metric space]
> If $\left(X_1, \rho_1\right)$ and $\left(X_2, \rho_2\right)$ are metric spaces, a map $f: X_1 \rightarrow X_2$ is called **continuous at $x \in X$** if for every $\epsilon>0$ there exists $\delta>0$ such that $\rho_2(f(y), f(x))<\epsilon$ whenver $\rho_1(x, y)<\delta-$ in other words, such that $f^{-1}(B(\epsilon, f(x))) \supset B(\delta, x)$. The map $f$ is called **continuous** if it is continuous at each $x \in X_1$ and **uniformly continuous** if, in addition, the $\delta$ in the definition of continuity can be chosen independent of $x$.

> [!Proposition 0.23]
> $f: X_1 \rightarrow X_2$ is continuous iff $f^{-1}(U)$ is open in $X_1$ for every open $U \subset X_2$.

> [!def cauchy sequency]
> A sequence $\left\{x_n\right\}$ in a metric space $(X, \rho)$ is called **Cauchy** if $\rho\left(x_n, x_m\right) \rightarrow 0$ as $n, m \rightarrow \infty$.

> [!def complete subset]
> A subset $E$ of $X$ is called **complete** if every Cauchy sequence in $E$ converges and its limit is in $E$.

\For example, $\mathbb{R}^n$ (with the Euclidean metric) is complete, whereas $\mathbb{Q}^n$ is not.

> [!Proposition 0.24]
> A closed subset of a complete metric space is complete, and a complete subset of an arbitrary metric space is closed.

Page 15

> [!def distance between a point and a set / distance between sets]
> In a metric space $(X, \rho)$ we can define the distance from a point to a set and the distance between two sets. Namely, if $x \in X$ and $E, F \subset X$,
> $$  \begin{gathered} \rho(x, E)=\inf \{\rho(x, y): y \in E\}, \\ \rho(E, F)=\inf \{\rho(x, y): x \in E, y \in F\}=\inf \{\rho(x, F): x \in E\} . \end{gathered}  $$

Observe that, by Proposition $0.22, \rho(x, E)=0$ iff $x \in \bar{E}$.

> [!def diameter of a subset a metric space, bounded subset]
> We also define the **diameter** of $E \subset X$ to be
> $$ \operatorname{diam} E=\sup \{\rho(x, y): x, y \in E\} .  $$
> $E$ is called **bounded** if $\operatorname{diam} E<\infty$.

> [!def cover of a subset of a metric space]
> If $E \subset X$ and $\left\{V_\alpha\right\}_{\alpha \in A}$ is a family of sets such that $E \subset \bigcup_{\alpha \in A} V_\alpha,\left\{V_\alpha\right\}_{\alpha \in A}$ is called a cover of $E$, and $E$ is said to be covered by the $V_\alpha$ 's.

> [!def totally bounded set]
> $E$ is called totally bounded if, for every $\epsilon>0, E$ can be covered by finitely many balls of radius $\epsilon$.

Every totally bounded set is bounded, for if $x, y \in \bigcup_1^n B\left(\epsilon, z_j\right)$, say $x \in B\left(\epsilon, z_1\right)$ and $y \in B\left(\epsilon, z_2\right)$, then

$$

\rho(x, y) \leq \rho\left(x, z_1\right)+\rho\left(z_1, z_2\right)+\rho\left(z_2, y\right) \leq 2 \epsilon+\max \left\{\rho\left(z_j, z_k\right): 1 \leq j, k \leq n\right\} .

$$

(The converse is false in general.) If $E$ is totally bounded, so is $\bar{E}$, for it is easily seen that if $E \subset \bigcup_1^n B\left(\epsilon, z_j\right)$, then $\bar{E} \subset \bigcup_1^n B\left(2 \epsilon, z_j\right)$.

> [!0.25 Theorem]
> If $E$ is a subset of the metric space $(X, \rho)$, the following are equivalent:
> a. $E$ is complete and totally bounded.
> b. (**The Bolzano-Weierstrass Property**) Every sequence in E has a subsequence that converges to a point of $E$.
> c. (**The Heine-Borel Property**) If $\left\{V_\alpha\right\}_{\alpha \in A}$ is a cover of $E$ by open sets, there is a finite set $F \subset A$ such that $\left\{V_\alpha\right\}_{\alpha \in F}$ covers $E$.

Page 16

> [!def compact set in a metric space]
> A set $E$ that possesses the properties (a)-(c) of Theorem 0.25 is called compact.

Every compact set is closed (by Proposition 0.24) and bounded; the converse is false in general but true in $\mathbb{R}^n$.

> [!Proposition 0.26]
> Every closed and bounded subset of $\mathbb{R}^n$ is compact.

> [!def equivalent metrics]
> Two metrics $\rho_1$ and $\rho_2$ on a set $X$ are called equivalent if
$$ C \rho_1 \leq \rho_2 \leq C^{\prime} \rho_1 \text { for some } C, C^{\prime}>0 . $$

It is easily verified that equivalent metrics define the same open, closed, and compact sets, the same convergent and Cauchy sequences, and the same continuous and uniformly continuous mappings. Consequently, most results concerning metric spaces depend not on the particular metric chosen but only on its equivalence class.

# 0.7 Notes and References

Try not to rely on the continuum hypothesis for arguments in proofs, unless of course there is a breakthrough in set theory