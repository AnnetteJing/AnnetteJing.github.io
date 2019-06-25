---
title: The Cartan–Dieudonné Theorem
layout: singlePost
categories: [blog]
tags: [Cartan–Dieudonné, quadratic space]
---

This blog will be about one of the most covoluted proofs I have encountered during my undergraduate career: the proof of the [Cartan–Dieudonné Theorem](https://en.wikipedia.org/wiki/Cartan–Dieudonné_theorem) for general quadratic spaces. I will be following [Prof. Peter Clark's](http://math.uga.edu/~pete/) proof in his [notes](http://math.uga.edu/~pete/quadraticforms.pdf), but add more details that aren't so obvious to first-time readers. 

There are two purposes of this post:
1. Test out using MathJax and Kramdown for my blog
2. ~~Type down everything before I forget it all~~

Before delving into the proof, we need several definitions and (not necessarily elementary) results: 
- $$(V, H)$$ is a quadratic space if ..
$$(V, F)$$ is a finite-dimensional vector space, $$char(F) \neq 2$$, and $$H$$ is a symmetric bilinear form on $$V$$ with corresponding quadratic form $$Q$$. 
- $$T: (V, H_V) \to (W, H_W)$$ is an isometry if ..
$$T$$ is a linear bijection that preserves the structure of quadratic spaces, i.e.
$$
H_W(T(v_1), T(v_2)) = H_V(v_1, v_2) \ \forall v_1, v_2 \in V
$$



### Statement of the Theorem

Let $$(V, H)$$ be a nondegenerate quadratic space of dimension $$n$$. Then, every $$\sigma \in \mathcal{O}(V)$$ that is not the identity can be expressed as a product of $$n$$ reflections. 

