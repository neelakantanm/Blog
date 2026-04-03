---
layout: post
title: "Bernstein's Inequality"
date: 2026-04-02
usemathjax: true
jekyll.environment: True
---

Let $P_N$ be the Littlewood--Paley projection to frequency $N$.

**Theorem.** Fix $N \in 2^{\mathbb{Z}}$.

1. **Bernstein's inequality I**
   $$
   \|f_N\|_{L^q}
   \lesssim
   N^{\frac{d}{p}-\frac{d}{q}} \|f_N\|_{L^p},
   \qquad 1 \le p \le q \le \infty.
   $$

2. **Bernstein's inequality II**
   $$
   \||\nabla|^s f_N\|_{L^p}
   \sim
   N^s \|f_N\|_{L^p},
   \qquad 1 \le p \le \infty,\ s \in \mathbb{R}.
   $$

**Proof.**

For the first inequality, let $\psi$ be a Littlewood--Paley cutoff. By Young's convolution inequality, if
$$
\frac{1}{p} + \frac{1}{r} = \frac{1}{q} + 1,
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
d - \frac{d}{r} = \frac{d}{p} - \frac{d}{q},
$$
we obtain
$$
\|f_N\|_{L^q}
\lesssim
N^{\frac{d}{p}-\frac{d}{q}} \|f\|_{L^p}.
$$

To replace $\|f\|_{L^p}$ by $\|f_N\|_{L^p}$, choose a second cutoff $\widetilde{\psi}$ such that
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

For the second inequality, fix $s \in \mathbb{R}$. By definition,
$$
\widehat{|\nabla|^s f_N}(\xi)
=
|\xi|^s \psi\!\left(\frac{\xi}{N}\right)\widehat{f}(\xi)
=
N^s
\left[
\left|\frac{\xi}{N}\right|^s
\psi\!\left(\frac{\xi}{N}\right)
\right]\widehat{f}(\xi).
$$
Set
$$
\rho(\xi) = |\xi|^s \psi(\xi).
$$
Because $\psi$ is supported away from the origin, we have
$$
\rho \in C_c^\infty(\mathbb{R}^d \setminus \{0\}).
$$
Hence
$$
\widehat{|\nabla|^s f_N}(\xi)
=
N^s \rho\!\left(\frac{\xi}{N}\right)\widehat{f}(\xi),
$$
and therefore
$$
|\nabla|^s f_N
=
N^s \bigl(f * (N^d \check{\rho}(N\cdot))\bigr).
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
\||\nabla|^s f_N\|_{L^p}
\lesssim
N^s \|f_N\|_{L^p}.
$$

For the reverse inequality, apply the previous estimate with $-s$ in place of $s$ to $|\nabla|^s f_N$:
$$
\|f_N\|_{L^p}
=
\||\nabla|^{-s} |\nabla|^s f_N\|_{L^p}
\lesssim
N^{-s}\, \||\nabla|^s f_N\|_{L^p}.
$$
Thus
$$
N^s \|f_N\|_{L^p}
\lesssim
\||\nabla|^s f_N\|_{L^p}.
$$
Combining the two inequalities proves the result.
