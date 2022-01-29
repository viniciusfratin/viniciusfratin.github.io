---
layout: post
title:  "Complex-Differentiability and the Cauchy-Riemann Equations"
date:   2022-01-29 01:24:16 -0300
categories: mathematics
---

I find the connection between complex-differentiability and the Cauchy-Riemann equations beautiful, and I would like to share it.

Let's first recall the concept of real-differentiability for a real-valued function. 
Given a function $$f: \mathbb{R} \to \mathbb{R}$$ and a point $$x_0 \in \mathbb{R}$$, we say that **$$f$$ is real-differentiable at $$x_0$$** if
the limit

$$ \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h} $$

exists. This limit is then denoted $$f'(x_0)$$.

Translating the limit notation to its formal defition, the existence of $$f'(x_0)$$ is equivalent to saying that
**for every** positive real number $$\epsilon > 0$$, **there exists at least one** positive real number $$\delta > 0$$ such that, **for every** real number $$h$$ satisfying

$$
\begin{equation}
	|h| < \delta,
	\label{eq_h_delta}
\end{equation}
$$

we have that

$$
\begin{equation}
	\left| \frac{f(x_0 + h) - f(x_0)}{h} \right| < \epsilon.
	\label{eq_f_real_diff}
\end{equation}
$$

$$\eqref{eq_h_delta}$$,$$\eqref{eq_f_real_diff}$$