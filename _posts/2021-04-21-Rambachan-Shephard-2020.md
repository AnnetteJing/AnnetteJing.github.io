---
title: Econometric analysis of potential outcomes time series - instruments, shocks, linearity, and the causal response function
layout: singlePost
categories: [blog]
tags: [dynamic causality, intrumental variables, linearity, potential outcomes, time series, shocks]
---

This post is my personal study notes for the [paper](https://arxiv.org/pdf/1903.01637.pdf) by [Rambachan](https://asheshrambachan.github.io) and [Shephard](https://scholar.harvard.edu/shephard/home) (2020).
Since it is intended for personal use, I will not specify the meaning of each symbol I use.


### Potential outcome time series

#### Formal definition

- **Def 1.1**  $$W_{1:T}$$ is a _**treatment path**_ if <br>
$$support(W_t) = \mathcal{W} \subset \mathbb{R}^k$$ for each $$t = 1, ..., T$$ and $$\mathcal{W}$$ is compact. 

- **Def 1.2**  The _**potential outcome path**_ for $$\pmb{w_{1:T} \in \mathcal{W}^T}$$ is <br>
$$Y_{1:T}(w_{1:T}) = (Y_1(w_{1:T}), ..., Y_T(w_{1:T}))^\intercal$$,
where $$Y_t(\cdot): \mathcal{W}^T \to \mathbb{R}$$ are real-valued functions. 

- **Def 2** $$\pmb{(Y_{1:T}, W_{1:T})}$$ is a _**potential outcome time series**_ if 
it satisfies the following assumptions <br>
	- A1. Non-anticipating potential outcomes:  <br>
	For each $$t = 1, ..., T$$, $$Y_t(w_{1:t}, w_{t + 1:T}) \stackrel{as}{=} Y_t(w_{1:t}, w_{t + 1:T}')$$ for all $$w_{1:T} \in \mathcal{W}^T$$, $$w_{t + 1:T}') \in \mathcal{W}^{T - t}$$. <br>
	Intuitively, this means future treatment assignments $$W_{t + 1:T}$$ shouldn't affect current and past outcomes $$Y_{1:t}(W_{1:T})$$.  <br>
	With this assumption, we can write $$Y_t(w_{1:T}) \stackrel{as}{=} Y_t(w_{1:t})$$. 
	- A2. Outcome generation & time-$$t$$ information: <br>
	The observed sequence of outcomes is $$Y_{1:T} = Y_{1:T}(W_{1:T}) = (Y_1(W_{1:T}), Y_2(W_{1:T}), ..., Y_T(W_{1:T}))^\intercal = (Y_1(W_1), Y_2(W_{1:2}), ..., Y_T(W_{1:T}))^\intercal$$.
