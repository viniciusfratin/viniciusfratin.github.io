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

$$
\begin{equation}
	\lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}
	\label{eq_lim_diff}
\end{equation}
$$

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

It is of no use to us now to dive deep into each section from this definition. Instead, we will only need to focus on two important features.

First, in order to $$\eqref{eq_h_delta}$$ to make sense, we need an absolute value operation to be defined. Of course, in this case, this is the usual absolute value
for the real numbers.

Second, in order to $$\eqref{eq_f_real_diff}$$ to make sense, we need the following:

1. Sum values from the domain of $$f$$, due to the expression $$x_0 + h$$. Note that this $$h$$ is the same as the one in $$\eqref{eq_h_delta}$$, so a sufficient condition	for things to make sense is that both $$h$$ and	the elements from the function's domain should belong to some structure which enables taking sums and absolute values.
		
2. Subtract the values of the function $$f$$, due to the expression $$f(x_0 + h) - f(x_0)$$.
	
3. Divide the values of the function $$f$$ by the values of $$h$$, due to the expression $$\frac{f(x_0 + h) - f(x_0)}{h}$$. This requires the structure of the values
   of the function to be compatible with the structure of the domain of the function with respect to division.
		
4. Take the absolute value of the resulting division, which requires yet more structure.
	
The interesting thing is that if we simply substitute the real numbers, $$\mathbb{R}$$, by the complex numbers, $$\mathbb{C}$$, in our limit definition $$\eqref{eq_lim_diff}$$, 
then **everything still makes perfect sense**!

Indeed, for any two arbitrary complex numbers $$z = a + ib$$ and $$w = c + id$$, where $$a, b, c, d$$ are real numbers and $$i$$ is the imaginary unit, we have,
by definition,

* $$z + w = (a + c) + i(b + d)$$,

* $$z - w = (a - c) + i(b - d)$$,

* $$z \times w = (ac - bd) + i(ad + bc)$$,

* $$\frac{z}{w} = $$.