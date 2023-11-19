---
aliases: [Ch 1 - The Real and Complex number systems]
created: 2023-11-18T14:28:31-08:00
modified: 2023-11-18T15:12:54-08:00
tags: 
---
# Ch 1 - The Real and Complex number systems
- Starts with notions of the partial ordering of the rational numbers then will work up to the construction of the reals from it.
> [!def dedekind cuts]
> A set of rational numbers $\alpha$ is a cut if it satisfies
> 1) $\alpha$ contains at least one rational, but not every rational, i.e. there exists at least one $x \in \alpha$ where $x \in \mathbb{Q}$ and there exists $y \in \mathbb{Q}$ such that $y \not \in \alpha$.
> 2) If $p, q \in \mathbb{Q}$ with $q \in \alpha$ then for all $p < q$ then $p \in \mathbb{Q}$
> 3) $\alpha$ contains no largest rational, i.e. for all $p \in \alpha$ there exists a $q \in alpha$ such that $p < q$
- Rudin then shows that the set of rational cuts is an abelian group under addition
- Follows by showing that the set of rational cuts is an abelian group under multiplication
- Defines the ring of real numbers by the completion of all rational cuts [todo::revise]

