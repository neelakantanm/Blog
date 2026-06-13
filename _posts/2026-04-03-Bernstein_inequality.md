---
layout: post
title: "Bernstein's Inequalities"
date: 2026-04-03
comments: true
---
Bernstein inequalities are one of the most fundamental inequalities in Fourier analysis. The goal of this post is to give a simple proof sketch of the two Bernstein inequalitites as I believe that every analyst should see the proof at least once in their life (moreover, I couldn't find the full statement of the two inequalities online even though they are widely used).  There is also the classic Bernstein's ineaulity in probability theory [Bernstein's inequality](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory)), which isn't related to the one I am discussing here.

One of the basic ideas in Fourier analysis is about decomposing the frequency space into amenable pieces corresponding to the problem one is working on. 
For example, [Littlewood-Paley theory](https://en.wikipedia.org/wiki/Littlewood–Paley_theory) 
is based on dyadic decomposition of the frequency space, which is what we will focus on in this post. Heuristically, the first Bernstein inequality explains what hapens to the $$L^p$$ norm of a function when the function is truncated to its large frequencies $$2^N$$. The second Bernstein inequality says that $$W^{s,p}$$-Sobolev norm of a function truncated to a frequency $$2^N$$ asymptotically grows like $$N^s$$ times the $$L^p$$ norm of the truncated function. 


**Theorem.** Fix $$N \in 2^{\mathbb{Z}}$$, and let $$P_N$$ be the Littlewood-Paley projection to frequency $$2^N$$. 


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

For the reverse inequality, apply the previous estimate with $$-s$$ in place of $$s$$ to $$\nabla^s f_N$$:

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

Combining the two inequalities gives us the required result.