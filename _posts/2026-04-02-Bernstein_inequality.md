---
layout: post
title: "Bernstein's Inequality"
date: 2026-04-02
---

Let $P_{N}$ be the Littlewood-Paley projection to frequency $N$. 
\begin{theorem}
	Fix $N \in 2^{\ZZ}$. 
	\begin{enumerate}
		\item (Bernstein's inequality I) 
		\begin{align*} ||f_N||_{L^q} \lesssim N^{\frac{d}{p}- \frac{d}{q}}||f_{N}||_{L^{p}}, \ \text{for}\ 1 \leq p \leq q \leq \infty.\end{align*}
		\item (Bernstein's inequality II)
		\begin{align*} ||\nabla ^{s} f_{N}||_{L^p} \sim N^{s} ||f_{N}||_{L^{p}}, \text{for}\ 1\leq p\leq \infty, \ \text{and}\ s\in \RR. \end{align*} 
		\end{enumerate}
	\begin{proof}
		\begin{enumerate}
			\item 
		Consider a Littlewood-paley cutoff function $\psi$. By Young's convolution inequality for $\frac{1}{p}+ \frac{1}{r}= \frac{1}{q}+1$
		\begin{align*} ||f_{N}||_{L^p}&= ||f* N^d \widecheck{\psi}(N. )||_{L^q} \leq ||f||_{L^p} ||N^{d} \widecheck{\psi}(N.)||_{L^r}\leq  ||f||_{L^p} N^{d-\frac{d}{r}}||\widecheck{\psi}||_{L^r}&\\
		& \lesssim N^{\frac{d}{q} -\frac{d}{q}} ||f||_{L^q}.&\end{align*}
		This inequality is almost good but not enough as we need $f_N$ on the right handside. Now, consider the new Littlewood-Paley projection mutiplier $\tilde{\psi}$ given by $\tilde{\psi}= \sum_{N/2 \leq K \leq N} \psi(\frac{.}{K})$. Let, the corresponding projector be denoted by $\tilde{P}_N$. Observe that $\tilde{P}_N P_N= P_N$. 
		Observe that 
		\begin{align*}  f* \sum_{N/2 \leq K\leq N} K^{d} \widecheck{\psi}(K.) \sim N^d f* \sum_{N/2 \leq K\leq N} \widecheck{\psi}(K.) \end{align*}
		Hence, we can re-write the above argument by 
		\begin{align*} ||f_N||_{L^q} &= ||\tilde{P}_N f_{N}||_{L^q}= ||f_N* N^d \widecheck{\tilde{\psi}}(N. )||_{L^q} \leq ||f_N||_{L^p} ||N^{d} \widecheck{\psi}(N.)||_{L^r}\leq  ||f_N||_{L^p} N^{d-\frac{d}{r}}||\widecheck{\psi}||_{L^r}&\\
		& \lesssim N^{\frac{d}{q} -\frac{d}{q}} ||f_N||_{L^q}.&\end{align*}
		\item Fix $s\in\RR$. By definiton,
		\begin{align*} \widehat{|\nabla|^s f _N}(\xi) \sim |\xi|^{s}\psi_{N}(\xi)\widehat{f}(\xi)= N^{s}\left[\frac{|\xi|^s}{N^s} \psi\left(\frac{\xi}{N}\right)\right]\widehat{f}(\xi).\end{align*}
		Since, the support of $\psi$ is localized away from the origin, $\rho(\xi):= |\xi|^s \psi(\xi) \in C_{c}^{\infty}(\RR^d\begin{align*}ckslash \{0\})$ for any value of $s$. So, $\widehat{|\nabla|^s f_{N}(\xi)} \sim N^s \rho(\frac{\xi}{N}) \widehat{f}(\xi)$, hence
		\begin{align*} |\nabla|^s f_N = N^{s}\left[ N^d f * \widecheck{\rho}(N. ) \right].\end{align*}
		Thus,
		\begin{align*} \| |\nabla|^s f_{N}\|_{L^p} \lesssim N^s \|f\|_{L^p}\|^d\widecheck{\rho}(N.)\|_{L^1}= N^s||f||_{L^p}||\widecheck{\rho}||_{L^1} \lesssim N^{s}\|f\|_{L^p}.\end{align*}
		Now, to get $f_N$ on the right hand side use the same trick of flattened Littlewood-Paley projection $\tilde{P}_N$ as before. Now, to get the reverse inequality,
		\begin{align*} \widehat{f}_N(\xi) \sim (|\nabla|^{-s}|\nabla|^{s} f_N)\widehat{}(\xi)\end{align*}
		Thus, applying the inequality that we already have to $|\nabla|^{-s} |\nabla|^s f_N $ gives us 
		\begin{align*} \|f_N\|_{L^{p}} \sim \||\nabla|^{-s}|\nabla|^{s} f_N\|_{L^p} \lesssim N^{-s} \||\nabla|^sf\|_{L^p}.\end{align*}
		Thus we get $N^s\|f_{N}\|_{L^p}\lesssim \||\nabla|^s f_{N}\|_{L^p}$.
		\end{enumerate}
		\end{proof}
	\end{theorem}
