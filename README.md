# Pure Relative Structured Matrix Approximation with Square-Root Matvecs

## Abstract

Let $\mathcal{L}\subseteq\mathbb{R}^{n\times m}$ be any known $q$-dimensional linear matrix family, and let an unknown $A$ be accessible only through products $Ax$ and $A^\top y$. A recent result obtains a nearly optimal approximation from $\mathcal{L}$ in about $\sqrt q$ queries, but incurs factor three and additive error proportional to $\|A\|_F$. Whether sublinear query complexity can give pure $(1+\epsilon)$ relative error was left open. We resolve this problem with a polynomial-time, nonadaptive algorithm. For a Frobenius-orthonormal basis $B_1,\ldots,B_q$, form the basis-invariant partial trace $S_L=\sum_iB_iB_i^\top$. The algorithm queries the leading eigenspace of $S_L$ exactly from the left, then fits the remaining directions from a Gaussian right sketch. If $\lambda_j$ are the eigenvalues of $S_L$, its constant-success query complexity is 

$$
 \min_s\left\{s+C\left[ \begin{aligned} &\max\{1,\lambda_{s+1}\}\log^2(2q)\\ &+\lambda_{s+1}/\epsilon \end{aligned}\right]\right\}. 
$$

 The transposed profile is also available. Since $\lambda_{s+1}\le q/(s+1)$, every family admits pure relative error with $\widetilde O(\sqrt{q/\epsilon})$ queries, independent of ambient dimensions and $\|A\|_F/\mathrm{OPT}$. The key proof is a partial-trace covariance lemma for a Gaussian matrix-valued design. Exact high-leverage queries make its expected Hessian the identity, while the centered regression offset has variance only $O(\lambda_{s+1}\mathrm{OPT}^2/k)$. A median construction amplifies success without estimating residual norms. Finally, a symmetric Wishart lower bound for fixed-sparsity approximation yields $\Omega(\sqrt{q/\epsilon})$ adaptive two-sided queries when $q\epsilon$ is bounded below. Thus the universal rate is optimal up to logarithmic factors in this joint regime.

## Main results

**Proposition.** For every $a,b\ge1$, there is a linear family of dimension $q=a+b$ and a unit residual $R\perp\mathcal{L}$ such that 

$$
 V_R(R)=b, \qquad V_L(R)=a. 
$$

 When $a$ and $b$ are comparable, both global orientations have order-$q$ offset variance. Nevertheless, the spectral-split estimator removes all contamination with one exact query.

**Theorem.** For every $A\in\mathbb{R}^{n\times m}$, every $q$-dimensional linear family $\mathcal{L}$, and every $\epsilon\in(0,1)$, the better orientation of (eq. in paper) returns $\widehat B\in\mathcal{L}$ satisfying (eq. in paper) with probability at least $0.9$ using at most 

$$
 \min\{\mathsf Q_L(\epsilon),\mathsf Q_R(\epsilon)\} 
$$

 matvec queries. The query vectors are nonadaptive and the estimator runs in polynomial time.

**Proposition.** Among all rank-$s$ orthogonal projectors $P$, 

$$
 \min_{\operatorname{rank}(P)=s}\Lambda_L(P)=\lambda_{s+1}^L. 
$$

 Thus the leading eigenspace minimizes both random-query terms in (eq. in paper).

**Corollary.** Let $L_\epsilon=\log^2(2q)+1/\epsilon$. Constant-success pure relative error requires at most 

$$
 O\!\left(\sqrt{qL_\epsilon}+\log^2(2q)\right) =\widetilde O\!\left(\sqrt{q/\epsilon}\right) 
$$

 two-sided matvec queries.

## Keywords

matrix-vector queries, structured matrix approximation, relative error, sketching, partial trace, query complexity

## Files

- `aistats2027.sty`
- `fancyhdr.sty`
- `main.bbl`
- `main.pdf`
- `main.tex`
- `references.bib`
- `supplement.bbl`
- `supplement.pdf`
- `supplement.tex`
