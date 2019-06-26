---
title: The Cartan–Dieudonné Theorem
layout: singlePost
categories: [blog]
tags: [Cartan–Dieudonné, quadratic space]
---

This blog will be about one of the most covoluted proofs I have encountered during my undergraduate career: the proof of the [Cartan–Dieudonné Theorem](https://en.wikipedia.org/wiki/Cartan–Dieudonné_theorem) for general quadratic spaces. I will be following [Prof. Peter Clark's](http://math.uga.edu/~pete/) proof in his [notes](http://math.uga.edu/~pete/quadraticforms.pdf), but add more details that aren't so obvious to first-time readers. 

There are two purposes of this post:
1. Test out using MathJax and Kramdown for my blog
2. ~~Type everything down before I forget it all~~

Before delving into the proof, we need several definitions and (not necessarily elementary) results: 
- $$(V, H)$$ is a **quadratic space** if <br>
$$(V, F)$$ is a finite-dimensional vector space, $$char(F) \neq 2$$, and $$H$$ is a symmetric bilinear form on $$V$$ with the corresponding quadratic form $$Q$$ 
- Symmetric bilinear form $$H$$ on $$V$$ is **non-degenerate** if <br>
$$L_H: V \to V^* $$ defined such that $$L_H(x) = H(x, \cdot) \ \forall x \in V$$ is an isomorphism <br>
Subspace $$W$$ of $$V$$ is **non-degenerate** if <br>
$$H\vert_W$$, the restriction of $$H$$ to $$W$$, is non-degenerate
- $$T: (V, H_V) \to (W, H_W)$$ is an **isometry** if <br>
$$T$$ is a linear bijection that preserves the structure of quadratic spaces, 
i.e. $$H_W(T(v_1), T(v_2)) = H_V(v_1, v_2) \ \forall v_1, v_2 \in V$$
- 



### Statement of the Cartan–Dieudonné Theorem

Let $$(V, H)$$ be a nondegenerate quadratic space of dimension $$n$$. Then, every $$\sigma \in \mathcal{O}(V)$$ that is not the identity can be expressed as a product of at most $$n$$ reflections. 

* * *

This is a proof by induction, and the core idea is to prove that the inductive step holds for the following three cases (which are mutually exclusive and collectively exhaustive): 
- **Case 1:** $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x = 0_V$$
- **Case 2:** $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x$$ is anisotropic
- **Case 3:** $$\forall x \in V \setminus \{0_V\}$$, $$\sigma(x) - x \neq 0_V$$ and is isotropic

* * *

We begin by proving a preliminary result that can help us prove a lemma used in the inductive step for case 3.

##### Lemma 1

$$V$$ is hyperbolic, $$W$$ is a maximal totally isotropic subspace of $$V$$, then (i) $$W = W^\perp$$; and (ii) if $$\sigma \in \mathcal{O}(V)$$ and $$\sigma\vert_W = I_W$$, we have $$det(\sigma) = 1_F$$.

###### _Proof of Lemma 1:_

**Part (i):**

Given $$V$$ is hyperbolic, we have $$V \cong m \mathbb{H}$$ for some $$m \in \mathbb{N}$$ and $$dim(W) = m$$ since $$W$$ is maximal totally isotropic. 
Since $$H\vert_W = H_0^W$$, we have $$H(x, w) = 0_F \ \forall x, w \in W$$, which implies $$W \subset W^\perp$$. By Proposition 4.3 of Clark, $$dim(W^\perp) = dim(V) - dim(W) = 2m - m = m = dim(W)$$. Hence, $$W = W^\perp$$. 

**Part (ii):**

By Theorem 6.2 of Clark, there exists totally isotropic subspace $$W'$$ of $$V$$ and bases $$\beta \equiv \{\beta_1, ..., \beta_m\}$$, $$\beta' \equiv \{\beta_1', ..., \beta_m'\}$$ of $$W$$ and $$W'$$, respectively, such that $$W \cap W^\perp = \{0_V\}$$, $$H(\beta_i, \beta_j') = \delta_{i,j} \ \forall i, j = 1, ..., m$$, and $$V = W + W^\perp$$.  


* * *

##### Lemma 2

$$(V, H)$$ is a nondegenerate quadratic space of dimension $$n$$, $$\sigma \in \mathcal{O}(V)$$ satisfies Case 3, then $$n \geq 4$$, is even, and $$det(\sigma) = 1_F$$. 

###### _Proof of Lemma 2:_

  







* * *



###### _Proof of Cartan–Dieudonné:_


