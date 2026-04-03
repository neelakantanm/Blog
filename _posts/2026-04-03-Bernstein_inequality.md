---
layout: post
title: "Bernstein's Inequality"
date: 2026-04-03
comments: true
---
Bernstein inequalities are one of my favorite inequalies in Fourier analysis. Heuristically the first Bernstein inequality explains what hapens to the $$L^p$$ norm of the function when the function is truncated to its large frequencies. The second Bernstein inequality compares the growth of the $$W^{s,p}$$-Sobolev norm of the function to 
Let $$P_N$$ be the Littlewood-Paley projection to frequency $$N$$.

**Theorem.** Fix $$N \in 2^{\mathbb{Z}}$$.

1. **Bernstein's inequality I**

   $$
   \begin{aligned}
   \|f_N\|_{L^q}
   \lesssim
   N^{\frac{d}{p}-\frac{d}{q}} \|f_N\|_{L^p},
   \qquad 1 \le p \le q \le \infty.
   \end{aligned}
   $$

2. **Bernstein's inequality II**

   $$
   \begin{align}
   \|\nabla^s f_N\|_{L^p}
   \sim
   N^s \|f_N\|_{L^p},
   \qquad 1 \le p \le \infty,\ s \in \mathbb{R}.
   \end{align}
   $$

**Proof.**

For the first inequality, let $$\psi$$ be a Littlewood--Paley cutoff. By Young's convolution inequality, if

$$
\begin{align}
\frac{1}{p} + \frac{1}{r} = \frac{1}{q} + 1,
\end{align}
$$

then

$$
\begin{aligned}
\|f_N\|_{L^q}
&= \|f * (N^d \check{\psi}(N\cdot))\|_{L^q} \\
&\le \|f\|_{L^p}\, \|N^d \check{\psi}(N\cdot)\|_{L^r} \\
&= \|f\|_{L^p}\, N^{d-\frac{d}{r}} \|\check{\psi}\|_{L^r}.
\end{aligned}
$$

Since

$$
\begin{align}
d - \frac{d}{r} = \frac{d}{p} - \frac{d}{q},
\end{align}
$$

we obtain

$$
\begin{align}
\|f_N\|_{L^q}
\lesssim
N^{\frac{d}{p}-\frac{d}{q}} \|f\|_{L^p}.
\end{align}
$$

To replace $$\|f\|_{L^p}$$ by $$\|f_N\|_{L^p}$$, choose a second cutoff $$\widetilde{\psi}$$ such that
$$
\widetilde{P}_N P_N = P_N.
$$
Then
$$
f_N = \widetilde{P}_N f_N,
$$
so the same argument gives
$$
\|f_N\|_{L^q}
\lesssim
N^{\frac{d}{p}-\frac{d}{q}} \|f_N\|_{L^p}.
$$

For the second inequality, fix $$s \in \mathbb{R}$$. By definition,

$$
\begin{align}
\widehat{|\nabla|^s f_N}(\xi)
=
|\xi|^s \psi\!\left(\frac{\xi}{N}\right)\widehat{f}(\xi)
=
N^s
\left[
\left|\frac{\xi}{N}\right|^s
\psi\!\left(\frac{\xi}{N}\right)
\right]\widehat{f}(\xi).
\end{align}
$$

Set

$$
\begin{align}
\rho(\xi) = |\xi|^s \psi(\xi).
\end{align}
$$

Because $$\psi$$ is supported away from the origin, we have

$$
\begin{align}
\rho \in C_c^\infty(\mathbb{R}^d \setminus \{0\}).
\end{align}
$$

Hence

$$
\begin{align}
\widehat{|\nabla|^s f_N}(\xi)
=
N^s \rho\!\left(\frac{\xi}{N}\right)\widehat{f}(\xi),
\end{align}
$$

and therefore

$$
\begin{align}
|\nabla|^s f_N
=
N^s \bigl(f * (N^d \check{\rho}(N\cdot))\bigr).
\end{align}
$$

So

$$
\begin{aligned}
\||\nabla|^s f_N\|_{L^p}
&\le
N^s \|f\|_{L^p}\, \|N^d \check{\rho}(N\cdot)\|_{L^1} \\
&=
N^s \|f\|_{L^p}\, \|\check{\rho}\|_{L^1}.
\end{aligned}
$$

Applying the same flattening trick as above yields

$$
\begin{align}
\||\nabla|^s f_N\|_{L^p}
\lesssim
N^s \|f_N\|_{L^p}.
\end{align}
$$

For the reverse inequality, apply the previous estimate with $$-s$$ in place of $$s$$ to $$|\nabla^s f_N|$$:

$$
\begin{align}
\|f_N\|_{L^p}
=
\||\nabla|^{-s} |\nabla|^s f_N\|_{L^p}
\lesssim
N^{-s}\, \||\nabla|^s f_N\|_{L^p}.
\end{align}
$$

Thus

$$
\begin{align}
N^s \|f_N\|_{L^p}
\lesssim
\||\nabla|^s f_N\|_{L^p}.
\end{align}
$$

Combining the two inequalities proves the result.