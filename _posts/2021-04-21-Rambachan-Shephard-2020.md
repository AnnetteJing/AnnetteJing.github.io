---
title: Econometric analysis of potential outcomes time series - instruments, shocks, linearity, and the causal response function
layout: singlePost
categories: [blog]
tags: [dynamic causality, intrumental variables, linearity, potential outcomes, time series, shocks]
---

This post is my personal study notes for the [paper](https://arxiv.org/pdf/1903.01637.pdf) by [Rambachan](https://asheshrambachan.github.io) and [Shephard](https://scholar.harvard.edu/shephard/home) (2020).
Since it is intended for personal use, I will not specify the meaning of each symbol I use.


### Potential outcome time series

##### Formal definition

- **Def 1.1**  $$W_{1:T}$$ is a _**treatment path**_ if <br>
$$support(W_t) = \mathcal{W} \subset \mathbb{R}^k$$ for each $$t = 1, ..., T$$ and $$\mathcal{W}$$ is compact. 

- **Def 1.2**  The _**potential outcome path**_ for $$\pmb{w_{1:T} \in \mathcal{W}^T}$$ is <br>
$$Y_{1:T}(w_{1:T}) = (Y_1(w_{1:T}), ..., Y_T(w_{1:T}))^\intercal$$,
where $$Y_t(\cdot): \mathcal{W}^T \to \mathbb{R}$$ are real-valued functions. 

$$
\newcommand{\indep}{\perp\!\!\!\!\perp}
\newcommand{\iid}{\stackrel{iid}{\sim}}
\newcommand{\bbl}{\Big(}
\newcommand{\bbr}{\Big)}
\newcommand{\bbbl}{\Bigg(}
\newcommand{\bbbr}{\Bigg)}
\newcommand{\0}{\mathbf{0}}
\newcommand{\1}{\mathbf{1}}
$$

- **Def 2** $$\pmb{(Y_{1:T}, W_{1:T})}$$ is a _**potential outcome time series**_ if 
it satisfies the following assumptions
	- **A1. Non-anticipating potential outcomes:**
	For each $$t = 1, ..., T$$,
	\begin{align}
	Y_t(w_{1:t}, w_{t + 1:T}) 
	\stackrel{as}{=} Y_t(w_{1:t}, w_{t + 1:T}')
	\quad \forall w_{1:T} \in \mathcal{W}^T, \ w_{t + 1:T}') \in \mathcal{W}^{T - t}.
	\end{align}
	Intuitively, this means future treatment assignments $$W_{t + 1:T}$$ shouldn't affect current and past outcomes $$Y_{1:t}(W_{1:T})$$.  <br>
	With this assumption, we can write $$Y_t(w_{1:T}) \stackrel{as}{=} Y_t(w_{1:t})$$. 
	- **A2. Outcome generation & time-$$t$$ information:** 
	The observed sequence of outcomes is 
	\begin{align}
	Y_{1:T} 
	= Y_{1:T}(W_{1:T}) 
	= (Y_1(W_{1:T}), Y_2(W_{1:T}), ..., Y_T(W_{1:T}))^\intercal 
	= (Y_1(W_1), Y_2(W_{1:2}), ..., Y_T(W_{1:T}))^\intercal.
	\end{align}
	Since we observe $$(Y_{1:t}, W_{1:t})$$ at time $$t$$, we equip the process with its natural filtration: $$\mathcal{F}_t = \sigma(Y_{1:t}, W_{1:t})$$. 
	- **A3. Non-anticipating treatment paths:** 
	For each $$t = 1, ..., T$$, 
	\begin{align}
	(\{Y_{t:T}(W_{1:t - 1}, w_{t:T}) \equiv (Y_t(W_{1:t - 1}, w_t), Y_{t + 1}(W_{1:t - 1}, w_{t:t + 1}), ..., Y_T(W_{1:t - 1}, w_{t:T})) | w_{t:T} \in \mathcal{W}^{T - t + 1}\} \indep W_t) | \mathcal{F}_{t - 1}
	\end{align}
	and 
<!---
	\begin{align}
	(W_{t + 1:T} \indep W_t) | \mathcal{F}_{t - 1}.
	\end{align}
	This says that the current treatment $$W_t$$ does not depend on future potential treatments and future treatment assignments. 

- **E.g. 1 Autoregression** 
	\begin{align}
	\begin{pmatrix}
	Y_t(w_{1:t}) \\
	W_t
	\end{pmatrix}
	= \begin{pmatrix}
	\mu + \phi Y_{t - 1}(w_{1:t - 1}) + \beta_0 w_t \\
	\gamma + \theta W_{t - 1} + \delta Y_{t - 1}(W_{1:t - 1})
	\end{pmatrix} + 
	\begin{pmatrix}
	\varepsilon_t \\
	\eta_t
	\end{pmatrix}, 
	\quad
	\begin{pmatrix}
	\varepsilon_t \\
	\eta_t
	\end{pmatrix}
	\iid
	N
	\bbbl 
	\0_2,
	\begin{pmatrix}
	\sigma_\varepsilon^2 & \rho \sigma_\varepsilon \sigma_\eta \\
	\rho \sigma_\varepsilon \sigma_\eta & \sigma_\eta^2
	\end{pmatrix}
	\bbbr.
	\end{align}
-->

##### Special cases














