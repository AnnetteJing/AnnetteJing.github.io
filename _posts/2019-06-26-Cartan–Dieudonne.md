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
- __$$(V, H)$$__ is a __quadratic space__ if <br>
$$(V, F)$$ is a finite-dimensional vector space, $$char(F) \neq 2$$, and $$H$$ is a symmetric bilinear form on $$V$$ with the corresponding quadratic form $$Q$$ 
- Symmetric bilinear form $$\mathbf{H}$$ on $$V$$ is **non-degenerate** if <br>
$$L_H: V \to V^* $$ defined such that $$L_H(x) = H(x, \cdot) \ \forall x \in V$$ is an isomorphism <br>
Subspace $$\mathbf{W}$$ of $$V$$ is **non-degenerate** if <br>
$$H\vert_W$$, the restriction of $$H$$ to $$W$$, is non-degenerate
- $$\mathbf{T: (V, H_V) \to (W, H_W)}$$ is an **isometry** if <br>
$$T$$ is a linear bijection that preserves the structure of quadratic spaces, 
i.e. $$H_W(T(v_1), T(v_2)) = H_V(v_1, v_2) \ \forall v_1, v_2 \in V$$
- 



### Statement of the Theorem

Let $$(V, H)$$ be a nondegenerate quadratic space of dimension $$n$$. Then, every $$\sigma \in \mathcal{O}(V)$$ that is not the identity can be expressed as a product of $$n$$ reflections. 


This is a proof by induction, and the core idea is to prove that the inductive step holds for the following three cases (which are mutually exclusive and collectively exhaustive): 
- **Case 1:** $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x = 0_V$$
- **Case 2:** $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x$$ is anisotropic
- **Case 3:** $$\forall x \in V \setminus \{0_V\}$$, $$\sigma(x) - x \neq 0_V$$ and is isotropic

We begin by proving a lemma that will be used in the inductive step for case 3. 

##### Lemma 1

$$(V, H)$$ is a nondegenerate quadratic space of dimension $$n$$, $$\sigma \in \mathcal{O}(V)$$ satisfies Case 3, then $$n \geq 4$$, is even, and $$det(\sigma) = 1_F$$. 

_Proof for Lemma 1:_









