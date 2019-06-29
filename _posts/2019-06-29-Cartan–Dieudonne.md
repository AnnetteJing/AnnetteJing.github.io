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

Here is a list of notations that will be used:
- $$V, W$$ denotes vector spaces or subspaces over some field $$F$$.
- $$[T]_\beta^\gamma$$: matrix representation of linear map $$T: V \to W$$ with respect to bases $$\beta$$ of $$V$$ and $$\gamma$$ of $$W$$.
- $$\psi_\beta(H)$$: matrix representation of bilinear form $$H: V \times V \to F$$ with respect to basis $$\beta$$


Before delving into the proof, we need several definitions and (not necessarily elementary) results: 
- $$(V, H)$$ is a **quadratic space** if <br>
$$(V, F)$$ is a finite-dimensional vector space, $$char(F) \neq 2$$, and $$H$$ is a symmetric bilinear form on $$V$$ with the corresponding quadratic form $$Q$$ 
- Symmetric bilinear form $$H$$ on $$V$$ is **non-degenerate** if <br>
$$L_H: V \to V^* $$, defined as 
$$
\begin{equation*}
	L_H(x) = H(x, \cdot) \ \forall x \in V \text{,}
\end{equation*}
$$
is an isomorphism <br>
Subspace $$W$$ of $$V$$ is **non-degenerate** if <br>
$$H\vert_W$$, the restriction of $$H$$ to $$W$$, is non-degenerate

##### Proposition 3.1 of Clark
Let $$\beta$$ be any basis of $$V$$, then $$H$$ is non-degenerate iff $$\psi_\beta(H)$$ is invertible (non-singular).

- $$T: (V, H_V) \to (W, H_W)$$ is an **isometry** if <br>
$$T$$ is a linear bijection that preserves the structure of quadratic spaces, 
i.e. $$H_W(T(v_1), T(v_2)) = H_V(v_1, v_2) \ \forall v_1, v_2 \in V$$
- 





##### Theorem 6.2 of Clark

$$V$$ non-degenerate, $$W$$ is a totally isotropic subspace of $$V$$ with basis $$\beta \equiv \{\beta_1, ..., \beta_m\}$$, then <br>
(i) exists totally isotropic subspace $$W'$$ of $$V$$ with basis $$\beta' \equiv \{\beta_1', ..., \beta_m'\}$$ such that $$W \cap W' = \{0_V\}$$ and $$H(\beta_i, \beta_j') = \delta_{i,j} \ \forall i, j = 1, ..., m$$; <br>
(ii) $$W + W' \equiv span\{\beta, \beta'\} \cong m \mathbb{H}$$.



##### Result on P. 20 of Clark

$$V$$ is non-degenerate, then $$det(\sigma) = \pm 1_F \ \forall \sigma \in \mathcal{O}(V)$$. 





* * *

* * *


### Statement of the Cartan–Dieudonné Theorem

Let $$(V, H)$$ be a nondegenerate quadratic space of dimension $$n$$. Then, every $$\sigma \in \mathcal{O}(V)$$ that is not the identity can be expressed as a product of at most $$n$$ reflections. 

* * *

This is a proof by induction, and the core idea is to prove that the inductive step holds for the following three cases (which are mutually exclusive and collectively exhaustive): 
- **Case 1:**  $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x = 0_V$$
- **Case 2:**  $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x$$ is anisotropic
- **Case 3:**  $$\forall x \in V \setminus \{0_V\}$$, $$\sigma(x) - x \neq 0_V$$ and is isotropic

* * *

We begin by proving a preliminary result that can help us prove a [lemma](#lemma-2) used in the inductive step for case 3.

##### Lemma 1

$$V$$ is hyperbolic, $$W$$ is a maximal totally isotropic subspace of $$V$$, then <br>
(i) $$W = W^\perp$$; and <br>
(ii) if $$\sigma \in \mathcal{O}(V)$$ and $$\sigma\vert_W = I_W$$, we have $$det(\sigma) = 1_F$$.

##### _Proof of Lemma 1:_

###### Part (i):

Given $$V$$ is hyperbolic and $$W$$ is maximal totally isotropic, we have that $$V \cong m \mathbb{H}$$ for some $$m \in \mathbb{N}$$ and $$dim(W) = m$$. 
Since $$H\vert_W = H_0^W$$, $$H(x, w) = 0_F \ \forall x, w \in W$$, which implies $$W \subset W^\perp$$. By Proposition 4.3 of Clark, 

$$
\begin{align*}
	dim(W^\perp) &= dim(V) - dim(W) \\
	&= 2m - m = m = dim(W) \text{.}
\end{align*}
$$

Hence, $$W = W^\perp$$. 

###### Part (ii):

According to [Theorem 6.2 of Clark](#theorem-6.2-of-clark:), there exists totally isotropic subspace $$W'$$ of $$V$$ and bases $$\beta := \{\beta_1, ..., \beta_m\}$$, $$\beta' := \{\beta_1', ..., \beta_m'\}$$ of $$W$$ and $$W'$$, respectively, such that $$W \cap W^\perp = \{0_V\}$$, $$H(\beta_i, \beta_j') = \delta_{i,j} \ \forall i, j = 1, ..., m$$, and $$V = W + W^\perp$$. Clearly $$\gamma := \beta \cup \beta'$$ is a basis for $$V$$.  
By assumption, we have $$\sigma(x) = x$$ for every $$x \in W$$. Fix any $$y \in W'$$, then for every $$w \in W$$ we have 

$$
\begin{align*}
	H(w, \sigma(y) - y) &= H(w, \sigma(y)) - H(w, y) \\
	&= H(w, \sigma(y)) - H(\sigma(w), \sigma(y)) = 0_V \text{,}
\end{align*}
$$

where the last equality holds because $$\sigma$$ acts as the identity on $$W$$. This implies $$\sigma(y) - y \in W^\perp = W$$. 

Thus, for each $$y \in W'$$ there exists some $$w_y \in W$$ such that $$\sigma(y) = w_y + y$$. To keep notations simple, we denote $$w_{\beta_i'}$$ with $$w_i$$ and let $$M$$ be the $$m \times m$$ matrix whose $$i^{th}$$ column is the coordinate vector of $$w_i$$ with respect to $$\beta$$. The matrix representation of $$\sigma$$ with respect to $$\gamma$$ is 

$$
\begin{align*}
	[\sigma]_\gamma^\gamma &= \Big([\beta_1]_\gamma, ..., [\beta_m]_\gamma, [w_1 + \beta_1']_\gamma, ..., [w_m + \beta_m']_\gamma \Big) \\
	&= \begin{pmatrix} 
		I_m & M \\
		\mathbf{0}_{m \times m} & I_m
	   \end{pmatrix} \text{.}
\end{align*}
$$

It follows $$det(\sigma) = det(I_m) det(I_m) = 1_F$$. 

* * *

##### Lemma 2

$$(V, H)$$ is a nondegenerate quadratic space of dimension $$n$$, $$\sigma \in \mathcal{O}(V)$$ satisfies Case 3, then $$n \geq 4$$, is even, and $$det(\sigma) = 1_F$$. 

##### _Proof of Lemma 2:_

###### If $$n = 1$$:

In this case, $$V$$ can be spanned by any non-zero vector. Given anisotropic vectors are non-zero and $$det(\sigma) = \pm 1_F$$ by the [result on P. 20 of Clark](#result-on-p.-20-of-clark:), we have that for every anisotropic $$x \in V$$, $$[\sigma(x)]_x = \pm 1_F$$. This implies $$\sigma(x) = \pm x$$. 

We cannot have $$\sigma(x) = x$$ since it contradicts the assumption $$\sigma(x) - x = 0_V$$. 

However, if $$\sigma(x) = -x$$, 

$$
\begin{equation*}
	Q(\sigma(x) - x) = Q(-2_F x) = 4_F Q(x) \neq 0_F \text{,}
\end{equation*}
$$

contradicting the assumption that $$\sigma(x) - x$$ is isotropic. Note that $$4_F \neq 0_F$$ because $$char(F) \neq 2$$ and $$F$$ is an integral domain. 

###### If $$n = 2$$:

Fix any anisotropic $$x \in V$$. By assumption $$\sigma(x) \neq ax \ \forall a \in F$$, because $$\sigma(x) - x \neq 0_V$$ and if $$\sigma(x) = ax$$ for some $$a \in F \setminus \{1_F\}$$, 

$$
\begin{equation*}
	Q(\sigma(x) - x) = (a - 1_F)^2Q(x) \neq 0_F \text{,}
\end{equation*}
$$

contradicting the assumption that $$\sigma(x) - x$$ is isotropic. Given $$n = 2$$, this implies $$\beta := \{x, \sigma(x)\}$$ forms a basis for $$V$$. 

Observe that $$H(x, \sigma(x)) = Q(x)$$, because by the assumptions that $$\sigma(x) - x$$ is isotropic and $$\sigma$$ is an isometry (implies $$Q(\sigma(x)) = Q(x)$$) we have

$$
\begin{align*}
	0_F &= Q(\sigma(x) - x) = Q(\sigma(x)) - 2_F H(\sigma(x), x) + Q(x) \\
	&= 2_F (Q(x) - H(\sigma(x), x)) \text{.}
\end{align*}
$$

The matrix representation of $$H$$ with respect to $$\beta$$ is then

$$
\begin{equation*}
	\psi_\beta(H) = 
	\begin{pmatrix}
		Q(x) & Q(x) \\
		Q(x) & Q(x) 
	\end{pmatrix}
	\text{,}
\end{equation*}
$$

and hence $$det(\psi_\beta(H)) = 0_F$$. By [proposition 3.1 of Clark](#proposition-31-of-clark), $$H$$ is degenerate, which contradicts the premise that $$V$$ is a non-degenerate quadratic space. 

###### If $$n \geq 3$$:








* * *

### _Proof of Cartan–Dieudonné:_


