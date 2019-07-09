---
title: The Cartan–Dieudonné Theorem
layout: singlePost
categories: [blog]
tags: [Cartan–Dieudonné, quadratic space]
---

This blog will be about one of the most covoluted proofs I have encountered during my undergraduate career: the proof of the [Cartan–Dieudonné Theorem](https://en.wikipedia.org/wiki/Cartan–Dieudonné_theorem) for general quadratic spaces. I will be following [Prof. Peter Clark's](http://math.uga.edu/~pete/) proof in his [notes](http://math.uga.edu/~pete/quadraticforms.pdf), but add more details that aren't so obvious to first-time readers. A few theorems used are taken from the first chapter of [Algebraic Theory of Quadratic Forms](https://books.google.com.tw/books?id=YvyOLDeOYQgC&pg=PA1&hl=zh-TW&source=gbs_toc_r&cad=4#v=onepage&q&f=false) by [Prof. Tsit Yuen Lam](https://math.berkeley.edu/~lam/). 

There are two purposes of this post:
1. Test out using MathJax and Kramdown for my blog
2. ~~Type everything down before I forget it all~~

Here is a list of notations used:
- $$V, W, U$$ denote vector spaces or subspaces over some field $$F$$.
- $$[T]_\beta^\gamma$$ : matrix representation of linear map $$T: V \to W$$ with respect to bases $$\beta$$ of $$V$$ and $$\gamma$$ of $$W$$.
- $$\psi_\beta(H)$$ : matrix representation of bilinear form $$H: V \times V \to F$$ with respect to basis $$\beta$$
- $$f\vert_W$$: restriction of function $$f: V \to U$$ to $$W \subseteq V$$
- $$H\vert_W$$: restriction of bilinear form $$H: V \times V \to F$$ to $$W \subseteq V$$
- $$T_0^V$$: the zero transformation on $$V$$
- $$H_0^V$$: the zero bilinear form on $$V$$
- $$f(V)$$: the range of function $$f:V \to U$$
- $$det(f)$$: the determinant of any matrix representation of function $$f:V \to U$$ (this is well-defined because all representations are congruent to one another and hence have the same determinant)


Before delving into the proof, we need quite many definitions and (not necessarily elementary) results, most of which can be found in [Prof. Clark's notes](http://math.uga.edu/~pete/quadraticforms.pdf): 
- $$(V, H)$$ is a **quadratic space** if <br>
$$(V, F)$$ is a finite-dimensional vector space, $$char(F) \neq 2$$, and $$H$$ is a symmetric bilinear form on $$V$$ with the corresponding quadratic form $$Q$$.
- Symmetric bilinear form $$H$$ on $$V$$ is **non-degenerate** if <br>
$$L_H: V \to V^* $$, defined as 
$$
\begin{equation*}
	L_H(x) = H(x, \cdot) \ \forall x \in V \text{,}
\end{equation*}
$$
is an isomorphism. <br>
Subspace $$W$$ of $$V$$ is **non-degenerate** if <br>
$$H\vert_W$$ is non-degenerate. <br>
So when we say a quadratic space $$V$$ is non-degenerate, it means the bilinear form $$H$$ it's equipped with is non-degenerate. 

##### Proposition 3.1 of Clark
Let $$\beta$$ be any basis of $$V$$, then $$H$$ is non-degenerate iff $$\psi_\beta(H)$$ is invertible (non-singular).

- $$T: (V, H_V) \to (W, H_W)$$ is an **isometry** if <br>
$$T$$ is a linear bijection such that $$H_W(T(v_1), T(v_2)) = H_V(v_1, v_2) \ \forall v_1, v_2 \in V$$, i.e. $$T$$ preserves the structure of quadratic spaces.
- $$(V, H_V)$$ is isometric to $$(W, H_W)$$, $$V \cong W$$, if <br>
$$\exists$$ isometry $$T: (V, H_V) \to (W, H_W)$$. <br>
It can be shown easily that "$$\cong$$" is an equivalent relation.  
- **Orthogonal Group** of $$(V, H)$$, $$\mathcal{O}(V)$$ <br>
$$\mathcal{O}(V) := \{T \in GL(V) | T \text{ is an isometry}\}$$ where $$GL(V)$$ denotes the general linear group of vector space $$V$$. 


##### Result on P. 20 of Clark

$$V$$ is non-degenerate, then $$det(\sigma) = \pm 1_F \ \forall \sigma \in \mathcal{O}(V)$$. 


- $$S_1, S_2 \subseteq V$$ are **orthogonal** is <br>
$$H(x_1, x_2) = 0_F \ \forall x_1 \in S_1, \ x_2 \in S_2$$.
- **Orthogonal Complement** of $$S \subseteq V$$, $$S^\perp$$ <br>
$$S^\perp := \{x \in V | H(x, s) = 0_F \ \forall s \in S\}$$.
- **Radical** of $$S \subseteq V$$, $$rad(S)$$ <br>
$$rad(S) := S \cap S^\perp$$ (so $$rad(V) = V^\perp$$).
- **Orthogonal Direct Sum** of $$(V, H_V)$$ and $$(W, H_W)$$, $$(V \oplus W, H_{V \oplus W})$$ <br>
$$V \oplus W := V \times W$$, the Cartesian product of $$V$$ and $$W$$ <br>
$$H_{V \oplus W}((v_1, w_1), (v_2, w_2)) := H_V(v_1, v_2) + H_W(w_1, w_2)$$. <br>
By recognizing each element $$v \in V$$ as $$(v, 0_W)$$ and $$w \in W$$ as $$(0_V, w)$$, $$V \oplus W$$ is simply the direct sum of vector spaces $$V$$ and $$W$$ with the additional condition that $$V \perp W$$. <br>
For the sake of simplicity, we denote a repeated direct sum of the same space, $$\bigoplus_{i = 1}^m V$$, as $$m V$$ following on. 


##### Exercise 1 on P.10 of Clark

Subspace $$W$$ of $$V$$ is non-degenerate iff $$rad(W) = \{0_V\}$$. 


##### Result regarding isometries
If $$g$$ is an isometry, then the following holds: <br>
(i) $$g(V_1 \oplus V_2) = g(V_1) \oplus g(V_2)$$; <br>
(ii) $$g(U^\perp) = g(U)^\perp$$. 


##### Proposition 4.2 of Clark

$$W$$ is a non-degenerate subspace of $$V$$, then $$V = W \oplus W^\perp$$. 


##### Proposition 4.3 of Clark

$$V$$ is non-degenerate, $$W$$ is a subspace of $$V$$, then <br>
(i) $$dim(V) = dim(W) + dim(W^\perp)$$; <br>
(ii) $$W^{\perp\perp} = W$$. 


- $$x \in V \setminus \{0_V\}$$ **[an]isotropic** if <br>
$$Q(x) \equiv H(x, x) = 0_F$$ [$$\neq 0_F$$] <br>
$$(V, H)$$ is **[an]isotropic** if <br>
(i) $$V$$ is non-degenerate; <br>
(ii) $$\exists$$ [$$\nexists$$] isotropic $$x \in V \setminus \{0_V\}$$.
- $$W \subseteq V$$ is **totally isotropic** if <br>
$$\forall x \in W \setminus \{0_V\}$$ are isotropic. Other equivalent definitions include: <br>
(a) $$Q\vert_W = T_0^W$$; (b) $$H\vert_W = H_0^W$$; (c) $$W \subseteq W^\perp$$. 
- **Hyperbolic Plane**, $$\mathbb{H}$$ <br>
$$\mathbb{H} := (F^2, H)$$ where $$H(x, y) = 2_F^{-1}(x_1 y_2 + x_2 y_1) \ \forall x \equiv (x_1, x_2), y \equiv (y_1, y_2) \in F^2$$, or equivalently, $$Q(x) = x_1 x_2 \ \forall x \equiv (x_1, x_2) \in F^2$$. 
- $$(V, H)$$ is a **hyperbolic space** if <br>
$$V \cong m \mathbb{H}$$ for some $$m \in \mathbb{N}$$. 
- **Reflection** through an anisotropic vector $$v \in V$$, $$\tau_v$$ <br>
$$\tau_v(x) := x - 2_F \frac{H(x, v)}{Q(v)} v \ \forall x \in V$$. <br>
It isn't hard to show $$\tau_v \in \mathcal{O}(V)$$, $$\tau_v^2 = I_V$$, and $$det(\tau_v) = -1_F$$.  


##### Theorem 6.2 of Clark

$$V$$ is non-degenerate, $$W$$ is a totally isotropic subspace of $$V$$ with basis $$\beta := \{\beta_1, ..., \beta_m\}$$, then <br>
(i) exists totally isotropic subspace $$W'$$ of $$V$$ with basis $$\beta' := \{\beta_1', ..., \beta_m'\}$$ such that $$W \cap W' = \{0_V\}$$ and $$H(\beta_i, \beta_j') = \delta_{i,j} \ \forall i, j = 1, ..., m$$; <br>
(ii) $$W + W' \equiv span\{\beta, \beta'\} \cong m \mathbb{H}$$.


##### Witt Cancellation Theorem

$$V_1 \cong V_2$$, $$U_1 \oplus V_1 \cong U_2 \oplus V_2$$, then $$U_1 \cong U_2$$. 


##### Witt Decomposition Theorem

For any $$(V, H)$$, $$\exists ! I(V) \in \mathbb{N} \cup \{0\}$$, anisotropic $$(V', H')$$ such that $$V \cong rad(V) \oplus I(V) \mathbb{H} \oplus V'$$, where the anisotropic quadratic space $$V'$$ is unique up to an isometry class. 


- Subspace $$W$$ of $$V$$ is **maximal totally isotropic** if <br>
(i) $$W$$ is totally isotropic; <br>
(ii) Any subspace $$U$$ of $$V$$ that contains $$W$$ is not totally isotropic.


##### Exercise 12 of Lam Ch1
$$V \cong n \mathbb{H}$$, then exist maximal totally isotropic subspaces $$W$$ and $$W'$$ of $$V$$ such that $$dim(W) = dim(W') = n$$ and $$V = W + W'$$. 


##### Corollary 4.4 of Lam Ch1

$$V$$ is non-degenerate, $$W$$ is a maximal totally isotropic subspace of $$V$$, then $$I(V) = dim(W)$$. <br>
(Note: This result can also be found on P. 17 of Clark, but the proof is left as an exercise for the reader.)


* * *
* * *


### Statement of the Cartan–Dieudonné Theorem

Let $$(V, H)$$ be a nondegenerate quadratic space of dimension $$n$$. Then, every $$\sigma \in \mathcal{O}(V)$$ that is not the identity can be expressed as a product of at most $$n$$ reflections. 

* * *

This is a proof by induction, and the core idea is to prove that the inductive step holds for the following three cases (which are mutually exclusive and collectively exhaustive): 
- **Case 1:**  $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x = 0_V$$
- **Case 2:**  $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x$$ is anisotropic
- **Case 3:**  $$\forall$$ anisotropic $$x \in V \setminus \{0_V\}$$, $$\sigma(x) - x \neq 0_V$$ and is isotropic

* * *

We begin by proving a preliminary result that can help us prove a [lemma](#lemma-2) used in the inductive step for case 3.

##### Lemma 1

$$V$$ is hyperbolic, $$W$$ is a maximal totally isotropic subspace of $$V$$, then <br>
(i) $$W = W^\perp$$; and <br>
(ii) if $$\sigma \in \mathcal{O}(V)$$ and $$\sigma\vert_W = I_W$$, we have $$det(\sigma) = 1_F$$.

##### _Proof of Lemma 1:_

###### Part (i):

Given $$V$$ is hyperbolic and $$W$$ is maximal totally isotropic, we have that $$V \cong m \mathbb{H}$$ for some $$m \in \mathbb{N}$$ and $$dim(W) = m$$ by [Exercise 12 and Corollary 4.4 of Lam Ch1](#exercise-12-of-lam-ch1). 
Since $$H\vert_W = H_0^W$$, $$H(x, w) = 0_F \ \forall x, w \in W$$. This implies $$W \subseteq W^\perp$$. By [Proposition 4.3 of Clark](#proposition-43-of-clark), 

$$
\begin{align*}
	dim(W^\perp) &= dim(V) - dim(W) \\
	&= 2m - m = m = dim(W) \text{.}
\end{align*}
$$

Hence, $$W = W^\perp$$. 

###### Part (ii):

According to [Theorem 6.2 of Clark](#theorem-6.2-of-clark), there exists totally isotropic subspace $$W'$$ of $$V$$ and bases $$\beta := \{\beta_1, ..., \beta_m\}$$, $$\beta' := \{\beta_1', ..., \beta_m'\}$$ of $$W$$ and $$W'$$, respectively, such that $$W \cap W^\perp = \{0_V\}$$, $$H(\beta_i, \beta_j') = \delta_{i,j} \ \forall i, j = 1, ..., m$$, and $$V = W + W^\perp$$. Clearly $$\gamma := \beta \cup \beta'$$ is a basis for $$V$$.  
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

In this case, $$V$$ can be spanned by any non-zero vector. Given anisotropic vectors are non-zero and $$det(\sigma) = \pm 1_F$$ by the [result on P. 20 of Clark](#result-on-p20-of-clark), we have that for every anisotropic $$x \in V$$, $$[\sigma(x)]_x = \pm 1_F$$. This implies $$\sigma(x) = \pm x$$. 

We cannot have $$\sigma(x) = x$$ since it contradicts the assumption $$\sigma(x) - x = 0_V$$. 

However, if $$\sigma(x) = -x$$, 

$$
\begin{equation*}
	Q(\sigma(x) - x) = Q(-2_F x) = 4_F Q(x) \neq 0_F \text{,}
\end{equation*}
$$

which contradicts the assumption that $$\sigma(x) - x$$ is isotropic. Note that $$4_F \neq 0_F$$ because $$char(F) \neq 2$$ and $$F$$ is an integral domain. 

###### If $$n = 2$$:

Fix any anisotropic $$x \in V$$. By assumption $$\sigma(x) \neq ax \ \forall a \in F$$, because $$\sigma(x) - x \neq 0_V$$ and if $$\sigma(x) = ax$$ for some $$a \in F \setminus \{1_F\}$$, 

$$
\begin{equation*}
	Q(\sigma(x) - x) = (a - 1_F)^2Q(x) \neq 0_F \text{,}
\end{equation*}
$$

again contradicting the assumption that $$\sigma(x) - x$$ is isotropic. Given $$n = 2$$, this implies $$\beta := \{x, \sigma(x)\}$$ forms a basis for $$V$$. 

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

and hence $$det(\psi_\beta(H)) = 0_F$$. By [Proposition 3.1 of Clark](#proposition-31-of-clark), $$H$$ is degenerate, which contradicts the premise that $$V$$ is a non-degenerate quadratic space. 

###### If $$n \geq 3$$:

First, we show that $$Q(\sigma(x) - x) = 0_F \ \forall x \in V$$, rather than just for anisotropic vectors. 
Given $$V$$ is non-degenerate, we have by [Exercise 1 on P.10 of Clark](#exercise-1-on-p10-of-clark) and [Witt Decomposition Theorem](#witt-decomposition-theorem) that 

$$
\begin{equation*}
	V = I(V) \mathbb{H} \oplus V' \equiv \bigoplus\limits_{i = 1}^{I(V)} \mathbb{H}_i \oplus V'
\end{equation*}
$$ 

for some anisotropic subspace $$V' \subseteq V$$. 

Take any isotropic $$y \in V \setminus \{0_V\}$$, then $$y$$ must belong into one of the hyperbolic planes. Assume without loss of generality that $$y \in \mathbb{H}_1$$ and let $$U := \bigoplus_{i = 2}^{I(V)} \mathbb{H}_i \oplus V'$$, then $$V = \mathbb{H}_1 \oplus U$$. 

Pick an anisotropic vector $$z \in U$$ (which must exist because neither hyperbolic spaces nor anisotropic spaces are totally isotropic). Clearly $$Q(z) \neq 0_F$$ and $$H(y, z) = 0_F$$. 
Then, for any $$a \in F \setminus \{0_F\}$$, 

$$
\begin{align*}
	Q(y + az) &= Q(y) + 2_F a H(y, z) + a^2 Q(z) \\
	&= a^2 Q(z) \neq 0_F \text{,}
\end{align*}
$$

we have that $$y + az$$ is anisotropic. 

It then follows after the assumption that 

$$
\begin{align*}
	0_F &= Q(\sigma(y + az) - (y + az)) = Q((\sigma(y) - y) + a(\sigma(z) - z))\\
	&= Q(\sigma(y) - y) + 2_F a H(\sigma(y) - y, \sigma(z) - z) + a^2 Q(\sigma(z) - z) \\
	&= Q(\sigma(y) - y) + 2_F a H(\sigma(y) - y, \sigma(z) - z) \text{,}
\end{align*}
$$

where the last equality holds because $$z$$ was chosen to be anisotropic. 
We set $$a = 1_F$$ and then $$a = -1_F$$, and sum the two resulting equations, which gives us

$$
\begin{equation*}
	2_F Q(\sigma(y) - y) = 0_F \text{.}
\end{equation*}
$$

Since $$y$$ is aribitrarily chosen, we have $$Q(\sigma(y) - y) = 0_F \ \forall y \in V$$. 


Now define $$W := (\sigma - I_V)(V)$$. By the previous result, 

$$
\begin{equation*}
	Q\vert_W = T_0^W \text{,}
\end{equation*}
$$

which means $$W$$ is totally isotropic and hence $$W \subseteq W^\perp$$. 

To prove $$W^\perp \subseteq W$$ we shall simply show $$W^\perp$$ is totally isotropic, because given $$V$$ is non-degenerate this gives $$W^\perp \subseteq W^{\perp\perp} = W$$ (see [Exercise 1 on P.10 of Clark](#exercise-1-on-p10-of-clark)).

Fix any $$y \in W^\perp$$. For every $$v \in V$$, 

$$
\begin{align*}
	H(v, \sigma(y) - y) &= H(\sigma(v), \sigma(y) - y) - H(\sigma(v) - v, \sigma(y) - y) \\
	&= H(\sigma(v), \sigma(y) - y) \text{  since } Q\vert_W = T_0^W \text{ implies } H\vert_W = H_0^W \\
	&= H(\sigma(v), \sigma(y)) - H(\sigma(v), y) \\
	&= H(v, y) - H(\sigma(v), y) \text{  because } \sigma \in \mathcal{O}(V) \\
	&= H(v - \sigma(v), y) = 0_F \text{  since } v - \sigma(v) \in W \text{ and } y \in W^\perp \text{.}
\end{align*}
$$

Therefore, $$\sigma(y) - y \in rad(V)$$ and by [Exercise 1 on P.10 of Clark](#exercise-1-on-p10-of-clark) $$\sigma(y) - y = 0_V$$. This means $$y$$ must be isotropic, otherwise the assumption that $$\sigma(x) - x \neq 0_V$$ for every anisotropic $$x \in V$$ won't hold. 
Since this is true for any $$y \in W^\perp$$, $$W^\perp$$ is totally isotropic and based on our reasoning above $$W = W^\perp$$. 

It follows immediately after [Proposition 4.3 of Clark](#proposition-43-of-clark) and our previous result that 

$$
\begin{equation*}
	n = dim(V) = dim(W) + dim(W^\perp) = 2 dim(W) \text{,}
\end{equation*}
$$

which implies $$n$$ is even and $$\geq 4$$. 

Finally, we show $$det(\sigma) = 1_F$$ using [Lemma 1](#lemma-1). 
Recall that we have shown $$W$$ is totally isotropic and $$\sigma(y) - y = 0_V \ \forall y \in W^\perp$$. 
The first result coupled with [Corollary 4.4 of Lam Ch1](#corollary-44-of-lam-ch1) implies that 

$$
\begin{equation*}
	2 dim(W) \leq 2 I(V) = dim(I(V) \mathbb{H}) < dim(I(V) \mathbb{H} \oplus U) \text{,}
\end{equation*}
$$

where $$U$$ is an aribitrary anisotropic subspace of $$V$$. 
Since $$dim(V) = 2 dim(W)$$, this means $$V \cong I(V) \mathbb{H}$$ and $$W$$ is maximal totally isotropic by [Exercise 12 of Lam Ch1](#exercise-12-of-lam-ch1). 

By part (i) of [Lemma 1](#lemma-1), $$W = W^\perp$$. Then, our second result becomes $$\sigma(y) - y = 0_V \ \forall y \in W$$, which is equivalent to $$\sigma\vert_W = I_W$$. Thus, by part (ii) of [Lemma 1](#lemma-1) we have $$det(\sigma) = 1_F$$. 


* * *

We can now finally begin our proof of the main theorem! As mentioned previously, this will be a proof by induction on $$dim(V)$$. 

### _Proof of Cartan–Dieudonné:_

###### (i) Base case: $$dim(V) = 1$$. 

When $$dim(V) = 1$$, $$V = span\{x\}$$ for some $$x \neq 0_V$$. As in the first part of the proof for [Lemma 2](#lemma-2), $$\sigma(x) = \pm x$$. Since every element in $$span\{x\}$$ are of the form $$ax$$ for some $$a \in F$$, this implies 

$$
\begin{equation*}
	\sigma(v) = \pm v \quad \forall v \in V \text{,}
\end{equation*}
$$

in other words, $$\sigma = I_V$$ or $$\sigma = -I_V$$. Given $$\sigma \neq I_V$$, the latter must hold. It can be easily verfied from its definition that $$\tau_x(ax) = -ax$$ for any $$a \in F$$. Hence, $$\sigma = \tau_x$$. 


###### (ii) Induction step: $$dim(V) = n$$, the statement holds for any quadratic space with dimension less than n.

**Case 1:**  $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x = 0_V$$

Let $$W = span\{x\}^\perp$$. Notice that $$span\{x\}$$ is non-degenerate by [Proposition 3.1 of Clark](#proposition-31-of-clark) since

$$
\begin{equation*}
	\psi_x(H\vert_{span\{x\}}) = Q(x) \neq 0_F \text{.}
\end{equation*}
$$

It then follows after [Proposition 4.2 of Clark](#proposition-42-of-clark) that 

$$
\begin{equation*}
	V = span\{x\} \oplus W \text{.}
\end{equation*}
$$

Remember that an isometry preserves strucures of quadratic spaces it maps from and to, which include direct sums (see [result regarding isometries](#result-regarding-isometries)). Then, because $$\sigma$$ is surjective and $$\sigma(x) = x$$ by assumption, we have

$$
\begin{align*}
	span\{x\} \oplus W &= V = \sigma(V) \\
	&= span\{\sigma(x)\} \oplus \sigma(W) \\
	&= span\{x\} \oplus \sigma(W) \text{,}
\end{align*}
$$

and by [Witt Cancellation Theorem](#witt-cancellation-theorem) $$W = \sigma(W)$$. 
Given $$V$$ is finite-dimensional, this ensues that $$\sigma\vert_W \in \mathcal{O}(W)$$, i.e. $$\sigma\vert_W$$ is still an isometry. 

$$\sigma\vert_W \neq I_W$$, otherwise $$\sigma = I_V$$ as we already have by assumption that 

$$
\begin{equation*}
	\sigma(ax) = ax \quad \forall x \in span\{x\} \text{.}
\end{equation*}
$$

By the induction hypothesis, there exist reflections $$\tau_1, ..., \tau_m$$ through anisotropic vectors $$x_1, ..., x_m \in W$$ where $$m \leq n - 1$$ such that 

$$
\begin{equation*}
	\sigma\vert_W = \tau_1 \circ ... \circ \tau_m \text{.}
\end{equation*}
$$

It is obvious from the definition of a reflection through some anisotropic vector $$v$$ that $$\tau_v(z) = z$$ for any $$z \in span\{v\}^\perp$$. 
Since $$span\{x\} = W^\perp$$ (direct result of [Proposition 4.3 of Clark](#proposition-43-of-clark)), a repeated application of the aforementioned result gives 

$$
\begin{equation*}
	\sigma(ax) = ax = \tau_1 \circ ... \circ \tau_m(ax)
\end{equation*}
$$

for every $$ax \in span\{x\}$$. 
Hence, $$\sigma = \tau_1 \circ ... \circ \tau_m$$ for some $$m \leq n - 1$$. 


**Case 2:**  $$\exists$$ anisotropic $$x \in V \setminus \{0_V\}$$ such that $$\sigma(x) - x$$ is anisotropic

By assumption $$\tau_{\sigma(x) - x}$$ is defined. We only have to show $$\tau_{\sigma(x) - x}(\sigma(x)) = x$$, then $$\tau_{\sigma(x) - x} \circ \sigma$$ satisfies Case 1 and there exist reflections $$\tau_1, ..., \tau_m$$ where $$m \leq n - 1$$ such that 

$$
\begin{equation*}
	\tau_{\sigma(x) - x} \circ \sigma = \tau_1 \circ ... \circ \tau_m \text{.}
\end{equation*}
$$

Because the inverses of reflections are themselves, we have 

$$
\begin{align*}
	\sigma(x) &= \tau_{\sigma(x) - x}(x) \\
	&= \tau_{\sigma(x) - x} \circ \tau_1 \circ ... \circ \tau_m \text{,}
\end{align*}
$$

$$\sigma$$ is a product of at most $$n$$ reflections.

Now we return to show $$\tau_{\sigma(x) - x}(\sigma(x)) = x$$. 

$$
\begin{align*}
	2_F H(\sigma(x), \sigma(x) - x) &= 2_F [Q(\sigma(x)) - H(\sigma(x), x)] \\
	&= [Q(\sigma(x)) - H(\sigma(x), x)] + [Q(x) - H(\sigma(x), x)] \text{  since } \sigma \in \mathcal{O}(V) \\
	&= H(\sigma(x), \sigma(x) - x) + H(x - \sigma(x), x) \\
	&= Q(\sigma(x) - x) \text{.}
\end{align*}
$$

Plugging this into the definition of a reflection gives

$$
\begin{align*}
	\tau_{\sigma(x) - x}(\sigma(x)) &= \sigma(x) - \frac{2_F H(\sigma(x), \sigma(x) - x)}{Q(\sigma(x) - x)} (\sigma(x) - x) \\
	&= \sigma(x) - (\sigma(x) - x) = x \text{.}
\end{align*}
$$


**Case 3:**  $$\forall$$ anisotropic $$x \in V \setminus \{0_V\}$$, $$\sigma(x) - x \neq 0_V$$ and is isotropic

By [lemma 2](#lemma-2), we must have $$n \geq 4$$, is even, and $$det(\sigma) = 1_F$$ in this case. 
Furthermore, the contrapositive of the lemma implies that if an isometry's determinant is not $$1_F$$, then it must satisfy the conditions of either Case 1 or 2. 

Pick any reflection $$\tau$$ on $$V$$, and define $$\sigma' := \tau \circ \sigma \in \mathcal{O}(V)$$. 

$$
\begin{equation*}
	det(\sigma') = det(\tau) det(\sigma) = -1_F \cdot 1_F = -1_F \text{,}
\end{equation*}
$$

so $$\sigma'$$ satisfies the conditions of Case 1 or 2 and there exists $$m \leq n$$, reflections $$\tau_1, ..., \tau_m$$ such that $$\sigma' = \tau_1 \circ ... \circ \tau_m$$. 
Again because the inverses of reflections are themselves, 

$$
\begin{equation*}
	\sigma = \tau \circ \tau_1 \circ ... \circ \tau_m \text{.}
\end{equation*}
$$

Since $$m < n$$ we're done. Indeed, if $$m = n$$ we have by the fact $$n$$ is even that

$$
\begin{equation*}
	det(\sigma) = (-1_F)^{n + 1} = -1_F \text{,}
\end{equation*}
$$

but this contradicts the result $$det(\sigma) = 1_F$$ we have from [lemma 2](#lemma-2). 


And thus we have completed the proof. :)
