---
aliases: [1 Measures]
created: 2023-10-01T15:10:49-07:00
modified: 2023-11-13T20:51:00-08:00
tags: 
---
# 1 Measures

Basic concepts of measure theory and construction of measures on the real line

# 1.1 Introduction - the impossibility of ideal properties of a measure over $\mathbb{R}$

We want to measure sizes of subsets of a metric space. Ideally we would have the following properties:

i. If $E_1, E_2, \ldots$ is a finite or infinite sequence of disjoint sets, then

$\mu\left(E_1 \cup E_2 \cup \cdots\right)=\mu\left(E_1\right)+\mu\left(E_2\right)+\cdots$

ii. If $E$ is congruent to $F$ (that is, if $E$ can be transformed into $F$ by translations, rotations, and reflections), then $\mu(E)=\mu(F)$.

iii. $\mu(Q)=1$, where $Q$ is the unit cube

$Q=\left\{x \in \mathbb{R}^n: 0 \leq x_j<1 \text { for } j=1, \ldots, n\right\}$

However, this is not a tractable problem for all subsets of the real line, so we must then weaken one or more of these hypotheses.

If we were to weaken (i. additivity of countable sequences) so that we only consider finite unions, then limits/continuity would break. In addition, for dimensions greater than or equal to 3, additivity of finite sequences would be incompatible with (ii.) and (iii.) In 1924, Banach and Tarski proved that there does not exist $\mu: \mathcal{P}\left(\mathbb{R}^n\right) \rightarrow[0, \infty]$ that assigns positive, finite values to bounded open sets and satisfies (i) for finite sequences as well as (ii).

> [!Preposition: Banach Tarski Paradox, 1924]
Let $U$ and $V$ be arbitrary bounded open sets in $\mathbb{R}^n, n \geq 3$. There exist $k \in \mathbb{N}$ and subsets $E_1, \ldots, E_k, F_1, \ldots, F_k$ of $\mathbb{R}^n$ such that
> - the $E_j$ 's are disjoint and their union is $U$;
> - the $F_j$ 's are disjoint and their union is $V$;
> - $E_j$ is congruent to $F_j$ for $j=1, \ldots, k$.

Thus one can cut up a ball the size of a pea into a finite number of pieces and rearrange them to form a ball the size of the earth! Needless to say, the sets $E_j$ and $F_j$ are very bizarre. They cannot be visualized accurately, and their construction depends on the axiom of choice.

**The best relaxation is that we discard the requirement that $\mu$ be defined on all subsets of $\mathbb{R}$ and instead construct $\mu$ on a class of subsets of $\mathbb{R}$**

# 1.2 $\sigma$-algebras
> [!def algebra of sets on a set]
> Let $X$ be a nonempty set. An algebra of sets on $X$ is a nonempty collection $\mathcal{A}$ of subsets of $X$ that is closed under finite unions and complements; in other words, if $E_1, \ldots, E_n \in \mathcal{A}$, then $\bigcup_1^n E_j \in \mathcal{A}$; and if $E \in \mathcal{A}$, then $E^c \in \mathcal{A}$.

> [!def $\sigma$-algebra]
> A $\sigma$-algebra is an algebra that is closed under countable unions.

(Some authors use the terms field and $\sigma$-field instead of algebra and $\sigma$-algebra.)

>[!lemma: properties of algebras / $\sigma$-algebras]
If $\mathcal{A}$ is a algebra over $X$ then, $X, \emptyset \in \mathcal{A}.$ and $\mathcal{A}$ is closed under finite intersection. Additionally, if $\mathcal{A}$ is a $\sigma$-algebra over $x$ then $\mathcal{A}$ is closed under countable intersection.

Some examples of $\sigma$-algebras: If $X$ is any set, $\mathcal{P}(X)$ and $\{\varnothing, X\}$ are $\sigma$-algebras. For uncountable $X$,  the $\sigma$-algebra of countable or co-countable sets

> [!def $\sigma$ algebra of countable or co-countable sets]
> If $X$ is uncountable, then
> $\mathcal{A}=\left\{E \subset X: E \text { is countable or } E^c \text { is countable }\right\}$
> is a $\sigma$-algebra, called the $\sigma$-algebra of countable or co-countable sets. (The point here is that if $\left\{E_j\right\}_1^{\infty} \subset \mathcal{A}$, then $\bigcup_1^{\infty} E_j$ is countable if all $E_j$ are countable and is co-countable otherwise.)

Verify that the intersection of any family of $\sigma$-algebras on $X$ is a $\sigma$-algebra.

> [!def $\sigma$-algebra generated by $\mathcal{E}$]
> If $\mathcal{E}$ is any subset of $\mathcal{P}(X)$ there exists a unique smallest $\sigma$-algebra $\mathcal{M}(\mathcal{E})$ containing $\mathcal{E}$ that is the intersection of all $\sigma$-algebras containing $\mathcal{E}$. $\mathcal{M}(\mathcal{E})$ is called the $\sigma$-algebra generated by $\mathcal{E}$. $\mathcal{P}(X)$ satisfies this in the event that no smaller $\sigma$-algebra can be found

> [!Lemma 1.1]
> If $\mathcal{E} \subset \mathcal{M}(\mathcal{F})$ then $\mathcal{M}(\mathcal{E}) \subset \mathcal{M}(\mathcal{F})$.

Proof. $\mathcal{M}(\mathcal{F})$ is a $\sigma$-algebra containing $\mathcal{E}$; it therefore contains $\mathcal{M}(\mathcal{E})$.

> [!def Borel $\sigma$-algebra]
> If $X$ is any metric space, or more generally any topological space (see Chapter 4), the $\sigma$-algebra generated by the family of open sets in $X$ (or, equivalently, by the family of closed sets in $X$ ) is called the Borel $\sigma$-algebra on $X$ and is denoted by $\mathcal{B}_X$. Its members are called Borel sets. $\mathcal{B}_X$ thus includes open sets, closed sets, countable intersections of open sets, countable unions of closed sets, and so forth.

> [!def $G_\delta$,  $F_\sigma$, $G_{\delta\sigma}$, $F_{\sigma\delta}$, $G_{\delta\sigma\delta}$, ... ]
> - A countable intersection of open sets is called a $G_\delta$ set;
> - a countable union of closed sets is called an $\boldsymbol{F}_{\boldsymbol{\sigma}}$ set;
> - a countable union of $G_\delta$ sets is called a $\boldsymbol{G}_{\boldsymbol{\delta}}$ set;
> - a countable intersection of $F_\sigma$ sets is called an $\boldsymbol{F}_{\boldsymbol{\sigma} \delta}$ set
>
> We can induct on this definition to yield further subclasses of F and G sets

$\delta$ and $\sigma$ stand for the German Durchschnitt and Summe, that is, intersection and union.)

The Borel $\sigma$-algebra of the Real line is an object of interest that allows us to construct many reasonable measures.

> [!Proposition 1.2 generators of the Borel $\sigma$ algebra of the real line]
> $B_{\mathbb{R}}$ is generated by each of the following:
> a. the open intervals: $\mathcal{E}_1=\{(a, b): a<b\}$,
> b. the closed intervals: $\mathcal{E}_2=\{[a, b]: a<b\}$,
> c. the half-open intervals: $\mathcal{E}_3=\{(a, b]: a<b\}$ or $\mathcal{E}_4=\{[a, b): a<b\}$,
> d. the open rays: $\mathcal{E}_5=\{(a, \infty): a \in \mathbb{R}\}$ or $\mathcal{E}_6=\{(-\infty, a): a \in \mathbb{R}\}$,
> e. the closed rays: $\mathcal{E}_7=\{[a, \infty): a \in \mathbb{R}\}$ or $\mathcal{E}_8=\{(-\infty, a]: a \in \mathbb{R}\}$.

> [!def product $\sigma$-algebra]
> Let $\left\{X_\alpha\right\}_{\alpha \in A}$ be an indexed collection of nonempty sets, $X=\prod_{\alpha \in A} X_\alpha$, and $\pi_\alpha: X \rightarrow X_\alpha$ the coordinate maps. If $\mathcal{M}_\alpha$ is a $\sigma$-algebra on $X_\alpha$ for each $\alpha$, the product $\sigma$-algebra on $X$ is the $\sigma$-algebra generated by
> $\left\{\pi_\alpha^{-1}\left(E_\alpha\right): E_\alpha \in \mathcal{M}_\alpha, \alpha \in A\right\}$
> We denote this $\sigma$-algebra by $\bigotimes_{\alpha \in A} \mathcal{M}_\alpha$. (If $A=\{1, \ldots, n\}$ we also write $\bigotimes_1^n \mathcal{M}_j$ or $\left.\mathcal{M}_1 \otimes \cdots \otimes \mathcal{M}_n.\right)$

> [!Proposition 1.3]
> If $A$ is countable, then $\bigotimes_{\alpha \in A} \mathcal{M}_\alpha$ is the $\sigma$-algebra generated by $\left\{\prod_{\alpha \in A} E_\alpha: E_\alpha \in \mathcal{M}_\alpha\right\}$.

> [!Proposition 1.4]
> Suppose that $\mathcal{M}_\alpha$ is generated by $\mathcal{E}_\alpha, \alpha \in A$. Then $\bigotimes_{\alpha \in A} \mathcal{M}_\alpha$ is generated by $\mathcal{F}_1=\left\{\pi_\alpha^{-1}\left(E_\alpha\right): E_\alpha \in \mathcal{E}_\alpha, \alpha \in A\right\}$. If $A$ is countable and $X_\alpha \in \mathcal{E}_\alpha$ for all $\alpha, \bigotimes_{\alpha \in A} \mathcal{M}_\alpha$ is generated by $\mathcal{F}_2=\left\{\prod_{\alpha \in A} E_\alpha: E_\alpha \in \mathcal{E}_\alpha\right\}$.

> [!Proposition 1.5]
> Let $X_1, \ldots, X_n$ be metric spaces and let $X=\prod_1^n X_j$, equipped with the product metric. Then $\bigotimes_1^n \mathcal{B}_{X_j} \subset \mathcal{B}_X$. If the $X_j$ 's are separable, then $\bigotimes_1^n \mathcal{B}_{X_j}=\mathcal{B}_X$

> [!Corollary 1.6 ]
> $\mathcal{B}_{\mathbb{R}^n}=\bigotimes_1^n \mathcal{B}_{\mathbb{R}}$.

> [!def elementary family]
> We define an elementary family to be a collection $\mathcal{E}$ of subsets of $X$ such that
> - $\varnothing \in \mathcal{E}$,
> - if $E, F \in \mathcal{E}$ then $E \cap F \in \mathcal{E}$,
> - if $E \in \mathcal{E}$ then $E^c$ is a finite disjoint union of members of $\mathcal{E}$.

> [!Proposition 1.7]
> If $\mathcal{E}$ is an elementary family, the collection $\mathcal{A}$ of finite disjoint unions of members of $\mathcal{E}$ is an algebra.

> [!def measure on a measurable space]
> Let $X$ be a set equipped with a $\sigma$-algebra $\mathcal{M}$. A measure on $\mathcal{M}$ (or on $(X, \mathcal{M})$, or simply on $X$ if $\mathcal{M}$ is understood) is a function $\mu: \mathcal{M} \rightarrow[0, \infty]$ such that
> i. $\mu(\varnothing)=0$,
> ii. if $\left\{E_j\right\}_1^{\infty}$ is a sequence of disjoint sets in $\mathcal{M}$, then $\mu\left(\bigcup_1^{\infty} E_j\right)=\sum_1^{\infty} \mu\left(E_j\right)$ (countable additivity)

Note that condition (ii) countable additivity implies finite additive. Thus all measures are finitely additive

> [!def finitely additive measure]
> Let $X$ be a set equipped with a $\sigma$-algebra $\mathcal{M}$. A measure on $\mathcal{M}$ (or on $(X, \mathcal{M})$, or simply on $X$ if $\mathcal{M}$ is understood) is a function $\mu: \mathcal{M} \rightarrow[0, \infty]$ such that
> i. $\mu(\varnothing)=0$,
> ii. if $\left\{E_j\right\}_1^{n}$ is a sequence of disjoint sets in $\mathcal{M}$, then $\mu\left(\bigcup_1^{n} E_j\right)=\sum_1^{n} \mu\left(E_j\right)$ (finite additivity)

> [!def measurable space / measure space / measurable set]
> If $X$ is a set and $\mathcal{M} \subset \mathcal{P}(X)$ is a $\sigma$-algebra, $(X, \mathcal{M})$ is called a **measurable space** and the sets in $\mathcal{M}$ are called **measurable sets**. If $\mu$ is a measure on $(X, \mathcal{M})$, then $(X, \mathcal{M}, \mu)$ is called a **measure space**.

> [!def finite / $\sigma$-finite / semifinite measure]
> Let $(X, \mathcal{M}, \mu)$ be a measure space. These terms concern the "size" of $\mu$.
> - If $\mu(X)<\infty$ (which implies that $\mu(E)<\infty$ for all $E \in \mathcal{M}$ since $\left.\mu(X)=\mu(E)+\mu\left(E^c\right)\right), \mu$ is called **finite**.
> - If $X=\bigcup_1^{\infty} E_j$ where $E_j \in \mathcal{M}$ and $\mu\left(E_j\right)<\infty$ for all $j, \mu$ is called $\sigma$-finite. More generally, if $E=\bigcup_1^{\infty} E_j$ where $E_j \in \mathcal{M}$ and $\mu\left(E_j\right)<\infty$ for all $j$, the set $E$ is said to be **$\sigma$-finite** for $\mu$. ( $E$ is of $\sigma$-finite measure.)
> - If for each $E \in \mathcal{M}$ with $\mu(E)=\infty$ there exists $F \in \mathcal{M}$ with $F \subset E$ and $0<\mu(F)<\infty, \mu$ is called **semifinite**.

$\mu$ is finite $\implies$ $\mu$ is $\sigma$-finite $\implies$ $\mu$ is semifinite. The second implication Exercise 13

Most practical measures are $\sigma$-finite, and non-$\sigma$-finite measures exhibit pathological behavior

Several examples of measures

>[!Prop: Any positive function defines a measure through a pointwise sum]
>- Let $X$ be any nonempty set, $\mathcal{M}=\mathcal{P}(X)$, and $f$ any function from $X$ to $[0, \infty]$. Then $f$ determines a measure $\mu$ on $\mathcal{M}$ by the formula $\mu(E)=\sum_{x \in E} f(x)$. (For the definition of such possibly uncountable sums, see $\S 0.5$.)
>- The reader may verify that $\mu$ is semifinite iff $f(x)<\infty$ for every $x \in X$, and $\mu$ is $\sigma$-finite iff $\mu$ is semifinite and $\{x: f(x)>0\}$ is countable.

Two special cases are of this property are

>[!def counting measure]
> If $f(x)=1$ for all $x, \mu$ is called counting measure;

>[!Def dirac measure]
>If, for some $x_0 \in X, f$ is defined by $f\left(x_0\right)=1$ and $f(x)=0$ for $x \neq x_0$, $\mu$ is called the point mass or Dirac measure at $x_0$.

> [!theorem 1.8]
> 1.8 Theorem. Let $(X, \mathcal{M}, \mu)$ be a measure space.
> a. (Monotonicity) If $E, F \in \mathcal{M}$ and $E \subset F$, then $\mu(E) \leq \mu(F)$.
> b. (Subadditivity) If $\left\{E_j\right\}_1^{\infty} \subset \mathcal{M}$, then $\mu\left(\bigcup_1^{\infty} E_j\right) \leq \sum_1^{\infty} \mu\left(E_j\right)$
> c. (Continuity from below) If $\left\{E_j\right\}_1^{\infty} \subset \mathcal{M}$ and $E_1 \subset E_2 \subset \cdots$, then $\mu\left(\bigcup_1^{\infty} E_j\right)=\lim _{j \rightarrow \infty} \mu\left(E_j\right)$.
> d. (Continuity from above) If $\left\{E_j\right\}_1^{\infty} \subset \mathcal{M}, E_1 \supset E_2 \supset \cdots$, and $\mu\left(E_1\right)<\infty$, then $\mu\left(\bigcap_1^{\infty} E_j\right)=\lim _{j \rightarrow \infty} \mu\left(E_j\right)$.

>[!def null set]
>If $(X, \mathcal{M}, \mu)$ is a measure space, a set $E \in \mathcal{M}$ such that $\mu(E)=0$ is called a null set.

By subadditivity, note that any countable union of null sets is a null set.

>[!def almost everywhere]
>If a statement about points $x \in X$ is true except for $x$ in some null set, we say that it is true almost everywhere (abbreviated a.e.), or for almost every $x$. (If more precision is needed, we shall speak of a $\boldsymbol{\mu}$-null set, or $\boldsymbol{\mu}$-almost everywhere).

> [!def complete measure]
> A measure whose domain includes all subsets of null sets is called complete

Completeness of measures can often reduce technical issues related to existence of sets in a measurable space. This can always be done by enlarging the domain of $\mu$.

> [!theorem 1.9 any measure can be completed by adding all of the null sets to the measurable space]
> 1.9 Theorem. Suppose that $(X, \mathcal{M}, \mu)$ is a measure space. Let $\mathcal{N}=\{N \in \mathcal{\mathcal { M }} |\; \mu(N)=0\}$ and $\overline{\mathcal{M}}=\{E \cup F: E \in \mathcal{M}$ and $F \subset N$ for some $N \in \mathcal{N}\}$. Then $\overline{\mathcal{M}}$ is a $\sigma$-algebra, and there is a unique extension $\bar{\mu}$ of $\mu$ to a complete measure on $\overline{\mathcal{M}}$.

>[!def completion of measure/ completion of measurable space w.r.t. a measure]
>The measure $\bar{\mu}$ in Theorem 1.9 is called the completion of $\mu$, and $\overline{\mathcal{M}}$ is called the completion of $\mathcal{M}$ with respect to $\mu$.

# 1.4 Outer Measures
> [!def outer measure]
> An outer measure on a nonempty set $X$ is a function $\mu^*: \mathcal{P}(X) \rightarrow[0, \infty]$ that satisfies
> - $\mu^*(\varnothing)=0$,
> - $\mu^*(A) \leq \mu^*(B)$ if $A \subset B$,
> - $\mu^*\left(\bigcup_1^{\infty} A_j\right) \leq \sum_1^{\infty} \mu^*\left(A_j\right)$.

The most common way to obtain outer measures is to start with a family $\mathcal{E}$ of "elementary sets" on which a notion of measure is defined (such as rectangles in the plane) and then to approximate arbitrary sets "from the outside" by countable unions of members of $\mathcal{E}$. The precise construction is as follows.

> [!1.10 Proposition]
>  Let $\mathcal{E} \subset \mathcal{P}(X)$ and $\rho: \mathcal{E} \rightarrow[0, \infty]$ be such that $\varnothing \in \mathcal{E}, X \in \mathcal{E}$, and $\rho(\varnothing)=0$. For any $A \subset X$, define
> $$\mu^*(A)=\inf \left\{\sum_1^{\infty} \mu\left(E_j\right): E_j \in \varepsilon \text { and } A \subset \bigcup_1^{\infty} E_j\right\}$$
>
> Then $\mu^*$ is an outer measure.

>[!def $\mu^*$-measurability]
>The fundamental step that leads from outer measures to measures is as follows. If $\mu^*$ is an outer measure on $X$, a set $A \subset X$ is called $\mu^{\star}$-measurable if
>$$\mu^*(E)=\mu^*(E \cap A)+\mu^*\left(E \cap A^c\right) \text { for all } E \subset X$$
>Of course, the inequality $\mu^*(E) \leq \mu^*(E \cap A)+\mu^*\left(E \cap A^c\right)$ holds for any $A$ and $E$, so to prove that $A$ is $\mu^*$-measurable, it suffices to prove the reverse inequality. The latter is trivial if $\mu^*(E)=\infty$, so we see that $A$ is $\mu^*$-measurable iff
>$$\mu^*(E) \geq \mu^*(E \cap A)+\mu^*\left(E \cap A^c\right) \text { for all } E \subset X \text { such that } \mu^*(E)<\infty$$

> [!1.11 Carathéodory's Theorem]
> If $\mu^*$ is an outer measure on $X$, the collection $\mathcal{M}$ of $\mu^*$-measurable sets is a $\sigma$-algebra, and the restriction of $\mu^*$ to $\mathcal{M}$ is a complete measure.

Our first applications of Carathéodory's theorem will be in the context of extending measures from algebras to $\sigma$-algebras.

> [!def premeasure]
>  if $\mathcal{A} \subset \mathcal{P}(X)$ is an algebra, a function $\mu_0: \mathcal{A} \rightarrow[0, \infty]$ will be called a premeasure if
>- $\mu_0(\varnothing)=0$,
>- if $\left\{A_j\right\}_1^{\infty}$ is a sequence of disjoint sets in $\mathcal{A}$ such that $\bigcup_1^{\infty} A_j \in \mathcal{A}$, then $\mu_0\left(\bigcup_1^{\infty} A_j\right)=\sum_1^{\infty} \mu_0\left(A_j\right)$.
>
>In particular, a premeasure is finitely additive since one can take $A_j=\varnothing$ for $j$ large. The notions of finite and $\sigma$-finite premeasures are defined just as for measures. If $\mu_0$
>is a premeasure on $\mathcal{A} \subset \mathcal{P}(X)$, it induces an outer measure on $X$ in accordance with Proposition 1.10, namely,
>$$\mu^*(E)=\inf \left\{\sum_1^{\infty} \mu_0\left(A_j\right): A_j \in \mathcal{A}, E \subset \bigcup_1^{\infty} A_j\right\}$$

>[!1.13 Proposition]
>If $\mu_0$ is a premeasure on $\mathcal{A}$ and $\mu^*$ is defined by (1.12), then
>a. $\mu^* \mid \mathcal{A}=\mu_0 ;$
>b. every set in $\mathcal{A}$ is $\mu^*$ measurable.

> [!1.14 Theorem ]
> Let $\mathcal{A} \subset \mathcal{P}(X)$ be an algebra, $\mu_0$ a premeasure on $\mathcal{A}$, and $\mathcal{M}$ the $\sigma$-algebra generated by $\mathcal{A}$. There exists a measure $\mu$ on $\mathcal{N}$ whose restriction to $\mathcal{A}$ is $\mu_0$ - namely, $\mu=\mu^* \mid \mathcal{M}$ where $\mu^*$ is given by (1.12). If $\nu$ is another measure on $\mathcal{N}$ that extends $\mu_0$, then $\nu(E) \leq \mu(E)$ for all $E \in \mathcal{N}$, with equality when $\mu(E)<\infty$. If $\mu_0$ is $\sigma$-finite, then $\mu$ is the unique extension of $\mu_0$ to a measure on $\mathcal{M}$.

This allows us to extend premeasures to measures over sigma algebras with a notion of uniqueness that depends on whether whether $\mu$ is finite or $\sigma$-finite

# 1.5 Borel Measures on the real line

We generally want that the measure of an interval is its length.

> [!def borel measures on the real line]
> The family of measures on $\mathbb{R}$ whose domain is the Borel $\sigma$-algebra $\mathcal{B}_{\mathbb{R}}$  are called Borel measures on $\mathbb{R}$.

>[!def distribution function from a finite borel measure]
>$\mu$ is a finite Borel measure on $\mathbb{R}$, and let $F(x)=\mu((-\infty, x]).\quad F$ is sometimes called the distribution function of $\mu$.

Then the distribution function $F$ is increasing by Theorem 1.8a and right continuous by Theorem $1.8 \mathrm{~d}$ since $(-\infty, x]=\bigcap_1^{\infty}\left(-\infty, x_n\right]$ whenever $x_n \searrow x$. (Recall the discussion of increasing functions in $\S 0.5$.) Moreover, if $b>a,(-\infty, b]=(-\infty, a] \cup(a, b]$, so $\mu((a, b])=$ $F(b)-F(a)$. Our procedure will be to turn this process around and construct a measure $\mu$ starting from an increasing, right-continuous function $F$. The special case $F(x)=x$ will yield the usual "length" measure.

The building blocks for our theory will be the left-open, right-closed intervals in $\mathbb{R}$ - that is, sets of the form $(a, b]$ or $(a, \infty)$ or $\varnothing$, where $-\infty \leq a<b<\infty$. In this section we shall refer to such sets as h-intervals (h for "half-open"). Clearly the intersection of two h-intervals is an h-interval, and the complement of an h-interval is an h-interval or the disjoint union of two h-intervals. By Proposition 1.7, the collection $\mathcal{A}$ of finite disjoint unions of h-intervals is an algebra, and by Proposition 1.2 , the $\sigma$-algebra generated by $\mathcal{A}$ is $\mathcal{B}_{\mathbb{R}}$.

> [!def h-intervals]
> h-intervals ( $h$ for "half-open") the left-open, right-closed intervals in $\mathbb{R}$ - that is, sets of the form $(a, b]$ or $(a, \infty)$ or $\varnothing$, where $-\infty \leq a<b<\infty$. C

Note that the intersection of two h-intervals is an h-interval, and the complement of an h-interval is an h-interval or the disjoint union of two h-intervals. By Proposition 1.7, the collection $\mathcal{A}$ of finite disjoint unions of h-intervals is an algebra, and by Proposition 1.2 , the $\sigma$-algebra generated by $\mathcal{A}$ is $\mathcal{B}_{\mathbb{R}}$.

> [!1.15 Proposition]
> Let $F: \mathbb{R} \rightarrow \mathbb{R}$ be increasing and right continuous. If $\left(a_j, b_j\right]$ $(j=1, \ldots, n)$ are disjoint $h$-intervals, let
> $$\mu_0\left(\bigcup_1^n\left(a_j, b_j\right]\right)=\sum_1^n\left[F\left(b_j\right)-F\left(a_j\right)\right],$$
> and let $\mu_0(\varnothing)=0$. Then $\mu_0$ is a premeasure on the algebra $\mathcal{A}$.

This says that any such $F$ can be used to construct a premeasure over unions of h-intervals.

## Proof 1.15
---
- Well defined since if there exists distinct finite sequences of h intervals $\{I_i\}_i^n, \{J_i\}_i^n$s.t.$(a,b] = \bigcup_1^nI_i = \bigcup_1^n J_i$ then by relabeling we get $$\sum_i \mu_0(I_i) = \sum_{i,j} \mu_0(I_i \cap J_i) = \sum_j \mu_0(J_i)$$
- Showing the equality
	- "$\geq$": Take $\bigcup I_i \in \mathcal{A}$ where $I_i$ are all h intervals. Then by compactness, there exists a finite subsequence of h-intervals that are contained in $I$ then by subadditivity $\mu_0(I)=\mu_0\left(\bigcup_1^n I_j\right)+\mu_0\left(I \backslash \bigcup_1^n I_j\right) \geq \mu_0\left(\bigcup_1^n I_j\right)=\sum_1^n \mu_0\left(I_j\right)$ so in the limit, $\mu_0(I) \geq \sum \mu_0\left(I_j\right)$
	- "$\leq$": Use right continuity of $F$ open cover $(a_j, b_j + \delta_j)$ and finite subcover due to compactness of $I$ and give an epsilon of room $\mu_0(I) < F(b) - F(a + \delta) + \epsilon < \sum \mu(I_j) + 2\epsilon$ for in the limit $\epsilon \rightarrow 0$ $\mu_0(I) \leq \sum \mu(I_j)$. Also note edge cases $a = -\infty$ and $b = \infty$

We can extend the premeasure construction to borel measure
---
> [!1.16 Theorem.]
>  If $F: \mathbb{R} \rightarrow \mathbb{R}$ is any increasing, right continuous function, there is a unique Borel measure $\mu_F$ on $\mathbb{R}$ such that $\mu_F((a, b])=F(b)-F(a)$ for all $a, b$. If $G$ is another such function, we have $\mu_F=\mu_G$ iff $F-G$ is constant. Conversely, if $\mu$ is a Borel measure on $\mathbb{R}$ that is finite on all bounded Borel sets and we define
> $$F(x)= \begin{cases}\mu((0, x]) & \text { if } x>0, \\ 0 & \text { if } x=0, \\ -\mu((-x, 0]) & \text { if } x<0,\end{cases}$$
> then $F$ is increasing and right continuous, and $\mu=\mu_F$.

## Proof 1.16
- $F$ induces a premeasure on $\mathcal{A}$ by thrm 1.15. Then the borel sets generated by $\mathcal{A}$ have a $\sigma$-finite premeasure so by thrm 1.14 have uniqueness $\mu_F((a,b]) = F(b) - F(a)$ for all $a,b$.
- For converse use monotonicity of $\mu$ and continuity from above and below  for $F$ increasng and right continuous. Uniqueness from thrm 1.14

