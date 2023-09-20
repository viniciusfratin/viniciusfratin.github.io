---
layout: post
title:  "Complex-Differentiability and the Cauchy-Riemann Equations"
date:   2022-01-29 01:24:16 -0300
categories: mathematics
---

# Preliminary Comments
I find the connection between complex-differentiability and the Cauchy-Riemann equations to be profoundly beautiful and would like to give you a brief exposition of the subject.

The only assumption I make is that the reader has some basic knowledge about multivariable calculus and complex numbers.

These assumptions and the intent of the text reflect, in some way, the current state of my own knowledge about the subject, which is very limited. As such, I will not try to expose the
many completixities and caveats of Complex Analysis, so as to not deceive the reader by implying the existence of an expertise that I don't possess.  

# Complex-Differentiability and the Cauchy-Riemann Equations
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

Translating the limit notation to its formal definition, the existence of $$f'(x_0)$$ is equivalent to saying that
for every positive real number $$\epsilon > 0$$, there exists at least one positive real number $$\delta > 0$$ such that, for every real number $$h$$ satisfying

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

It is of no use for us to dive deep into the details of this definition. Instead, we will restrict out attention to two important features.

First, in order for $$\eqref{eq_h_delta}$$ to make sense, we need an absolute value operation to be defined. Of course, in this case, this is the usual absolute value operation
for the real numbers.

Second, in order for $$\eqref{eq_f_real_diff}$$ to make sense, we need to be able to:

1. Sum values from the domain of $$f$$, due to the expression $$x_0 + h$$. Note that this $$h$$ is the same as the one in $$\eqref{eq_h_delta}$$, so a sufficient condition	for things to make sense is that both $$h$$ and	the elements from the domain of the function should belong to some structure which enables taking sums and absolute values.
		
2. Subtract the values of the function $$f$$, due to the expression $$f(x_0 + h) - f(x_0)$$.
	
3. Divide the values of the function $$f$$ by the values of $$h$$, due to the expression $$\displaystyle \frac{f(x_0 + h) - f(x_0)}{h}$$. Therefore, the structure of the values
   of the function needs to be compatible with the structure of the domain of the function with respect to division.
		
4. Take the absolute value of the resulting division, which requires yet more structure.
	
The interesting thing is that if we simply substitute the real numbers, $$\mathbb{R}$$, by the complex numbers, $$\mathbb{C}$$, in our limit definition $$\eqref{eq_lim_diff}$$, 
then **everything still makes perfect sense**!

Indeed, for any two arbitrary complex numbers $$z = a + ib$$ and $$w = c + id$$, where $$a, b, c, d$$ are real numbers and $$i$$ is the imaginary unit, we have,
by definition,

* $$z + w = (a + c) + i(b + d)$$,

* $$z - w = (a - c) + i(b - d)$$,

* $$z \times w = (ac - bd) + i(ad + bc)$$,

* $$\displaystyle \frac{z}{w} = \frac{(ac + bd) + i(bc - ad)}{c^2+d^2}$$, only defined for $$w \neq 0$$ and

* $$ |z| = \sqrt{a^2 + b^2} $$
  .
  
These are all the operations that we need, and we can now state the definition of complex-differentiability.

Given a function $$f: \mathbb{C} \to \mathbb{C}$$ and a point $$z_0 \in \mathbb{C}$$, we say that the function **$$f$$ is complex-differentiable at $$z_0$$** when the limit

$$ 
\begin{equation}
	\lim_{h \to 0} \frac{f(z_0 + h) - f(z_0)}{h} 
	\label{eq_lim_complex_diff}
\end{equation}
$$

exists. This limit is then again denoted $$f'(z_0)$$.

Despite the formal similarities between real- and complex-differentiability, **complex-differentiability is a much stronger condition**. Of course, trying to compare $$\mathbb{R}$$ and $$\mathbb{C}$$ directly is kind of artificial, as $$\mathbb{R}$$ is 1-dimensional, while $$\mathbb{C}$$ is 2-dimensional. However, even when considering the natural analog of $$\mathbb{C}$$,
namely, $$\mathbb{R}^2$$ (on which the definition $$\eqref{eq_lim_diff}$$ for real-differentiability requires some technical adaptations which are not important for us right now), we can draw many more important conclusions from complex-differentiability than from
real-differentiability. The downside of these new possibilities is that there are, in some sense, fewer complex-differentiable functions than there are real-differentiable functions. However,
complex-differentiable functions are common enough and useful enough that the time and effort in studying them is completely worthwhile.

One example of the power of complex-differentiability is that, when a function is complex-differentiable at least **once** in an open disk around a point, then we can automatically conclude that it is complex-differentiable an
**infinite number of times** in this disk. Even more, the power series expansion for complex-differentiable functions in an open disk converges everywhere to the values of the function itself in this disk, so it is also **analytic** there! (**September 19th, 2023**: See correction note 1 at the end.) 

Just imagine trying to do the same for real-differentiable functions: let's consider the function $$f: \mathbb{R} \to \mathbb{R}$$ such that 

$$
f(x) = 
\begin{cases}
    -\frac{x^2}{2},		&\quad x < 0, \\
	0,	 				&\quad x = 0, \\
    \frac{x^2}{2},  	&\quad x > 0. \\ 
\end{cases}
$$

This function is everywhere differentiable with 
$$f'(x) = |x|$$,
which itself is **not** differentiable at $$x = 0$$. So we have a function which is real-differentiable once, but not twice. In particular, it is not infinitely differentiable.

What about the relation between real-differentiability and analicity of real functions? Well, consider the function $$f: \mathbb{R} \to \mathbb{R}$$ such that 

$$
f(x) = 
\begin{cases}
    e^{-\frac{1}{x^2}},		&\quad x \neq 0, 	\\
	0,	 					&\quad x = 0. 		\\ 
\end{cases}
$$

This function is actually everywhere infinitely differentiable. However, it is **non-analytic** at $$x=0$$, because every derivative is, in fact, zero at this point. Therefore, the power series expansion
around $$x = 0$$ is identically zero (because $$f(0) = 0$$ too) and, as such, does not match the values $$f(x)$$ for any $$x \neq 0$$.

Similar phenomena happen for functions in $$\mathbb{R}^2$$ when considering real-differentiability, and so we can start to appreciate the power of complex-differentiable functions.

Now, concerning our original topic, let's analyze the behavior of a complex-differentiable function (which we will simply call **differentiable function** from now on) at a single point.

Let $$f: \mathbb{C} \to \mathbb{C}$$ be a differentiable function at $$z = z_0$$. We can split $$f$$ into its real and imaginary parts as $$f(z) = u(z) + iv(z)$$, where $$u: \mathbb{C} \to \mathbb{R}$$
and $$v: \mathbb{C} \to \mathbb{R}$$ assume real values for complex inputs. Because $$f$$ is differentiable at $$z = z_0$$, the limit $$\eqref{eq_lim_complex_diff}$$ exists.
In particular, it means that this limit is equal to $$f'(z_0)$$ **regardless of the direction in which $$h$$ tends to $$0$$ in the complex plane**.

Then, let's first consider the case in which $$h$$ tends to zero along the real axis. Here, $$h = k$$, where $$k \in \mathbb{R}$$. By writing $$z_0 = x_0 + iy_0$$ and $$z = x + iy$$, we can further
write $$f(z) = f(x, y) = u(x, y) + iv(x, y)$$. Therefore,

$$
\lim_{h \to 0} \frac{f(z_0 + h) - f(z_0)}{h} = \lim_{k \to 0} \frac{f(x_0 + iy_0 + k) - f(x_0 + iy_0)}{k} = \lim_{k \to 0} \frac{f(x_0 + k, y_0) - f(x_0, y_0)}{k}.
$$

Carrying the manipulations,

$$
\lim_{k \to 0} \frac{f(x_0 + k, y_0) - f(x_0, y_0)}{k} = \lim_{k \to 0} \left[ \frac{u(x_0 + k, y_0) - u(x_0, y_0)}{k} + i\frac{v(x_0 + k, y_0) - v(x_0, y_0)}{k}\right].
$$

Note that the two quotients inside the limit are precisely the difference quotients for the partial derivatives of the functions $$u$$ and $$v$$ with respect to $$x$$. Then, by definition, we get

$$
\begin{equation}
	f'(z_0) = \lim_{h \to 0} \frac{f(z_0 + h) - f(z_0)}{h} = \frac{\partial u}{\partial x}(x_0, y_0) + i\frac{\partial v}{\partial x}(x_0, y_0).
	\label{eq_final_diff_real}
\end{equation}
$$

Now, let's do the same, but considering the case in which $$h$$ tens to zero along the complex axis. Here, $$h = ik$$, where $$k \in \mathbb{R}$$. Therefore,

$$
\lim_{h \to 0} \frac{f(z_0 + h) - f(z_0)}{h} = \lim_{k \to 0} \frac{f(x_0 + iy_0 + ik) - f(x_0 + iy_0)}{ik} = \lim_{k \to 0} \frac{f(x_0, y_0 + k) - f(x_0, y_0)}{ik}.
$$

Noting that $$\frac{1}{i} = -i$$ and carrying the manipulations as before, we get

$$
\lim_{k \to 0} \frac{f(x_0, y_0 + k) - f(x_0, y_0)}{ik} = -i \lim_{k \to 0} \left[ \frac{u(x_0, y_0 + k) - u(x_0, y_0)}{k} + i\frac{v(x_0, y_0 + k) - v(x_0, y_0)}{k}\right].
$$

This time, note that the two quotients inside the limit are precisely the difference quotients for the partial derivatives of the functions $$u$$ and $$v$$ with respect to $$y$$. Then, by definition, and
remembering that $$i^2 = -1$$, we conclude that

$$
\begin{equation}
	f'(z_0) = \lim_{h \to 0} \frac{f(z_0 + h) - f(z_0)}{h} = \frac{\partial v}{\partial y}(x_0, y_0) -i\frac{\partial u}{\partial y}(x_0, y_0).
	\label{eq_final_diff_imaginary}
\end{equation}
$$

By comparing $$\eqref{eq_final_diff_real}$$ and $$\eqref{eq_final_diff_imaginary}$$ and remembering that two complex numbers are equal if, and only if, their real and imaginary parts match, we finally get

$$
\boxed{
	\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}
}
$$

and

$$
\boxed{
	\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}.
}
$$

These are the famous **Cauchy-Riemann equations** and are, as we have just shown, necessary conditions for the differentiability of a complex function at a point. In other words, if the Cauchy-Riemann equations are **not**
both satisfied for two functions $$u$$ and $$v$$ at a point, then the function $$f=u+iv$$ is **not** differentiable at this point. (**September 19th, 2023**: See clarification note 1 at the end.)

In general, **the converse is not true**. That is, if $$u$$ and $$v$$ satisfy the Cauchy-Riemann equations, we **cannot** say that $$f=u+iv$$ is differentiable. However, under certain regularity
conditions (such as when $$u$$ and $$v$$ are both continuously real-differentiable), the converse holds. In this case, the Cauchy-Riemann equations provide an elegant characterization of complex-differentiable functions. (**September 19th, 2023**: See correction note 2 at the end.)

In some sense, one way that the Cauchy-Riemann equations show that complex-differentiability is a stronger condition than real-differentiability is by exposing direct relations between the partial derivatives of
the real and imaginary parts of the complex function, which is something that has no direct parallel in the study of real-differentiability of real functions.

# Correction notes

**Note 1**: The important remark that this condition needs to hold **in an open disk around the point**, and not only the point, was missing and was added.

**Note 2**: For the converse statement, one of the regularity conditions is that $$u$$ and $$v$$ must be continuosly real-differentiable. The continuity of the derivatives was missing and was added.

# Clarification notes

**Note 1**: it is important to remember that differentiability is something which applies to a single point, so this information was added.

# References

Wikipedia contributors. Cauchy–Riemann equations. In Wikipedia, The Free Encyclopedia. From [https://en.wikipedia.org/wiki/Cauchy%E2%80%93Riemann_equations](https://en.wikipedia.org/wiki/Cauchy%E2%80%93Riemann_equations)

Lars Ahlfors. Complex analysis (3rd ed.). McGraw Hill (published 1979). ISBN 0-07-000657-1

John Nachbar. Multivariate Differentiation. From [https://cpb-us-w2.wpmucdn.com/sites.wustl.edu/dist/3/2139/files/2019/09/mvdiff.pdf](https://cpb-us-w2.wpmucdn.com/sites.wustl.edu/dist/3/2139/files/2019/09/mvdiff.pdf)

Jean-Pierre Merx. Differentiability of Multivariable Real Functions (Part 1). From [https://www.mathcounterexamples.net/differentiability-multivariable-real-functions-part1/](https://www.mathcounterexamples.net/differentiability-multivariable-real-functions-part1/)

Jean-Pierre Merx. Differentiability of Multivariable Real Functions (Part 2). From [https://www.mathcounterexamples.net/differentiability-multivariable-real-functions-part2/](https://www.mathcounterexamples.net/differentiability-multivariable-real-functions-part2/)