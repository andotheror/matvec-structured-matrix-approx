# Pure Relative Structured Matrix Learning with Square-Root Matvecs

## Abstract

Let $\mathcal L\subseteq\mathbb R^{n\times m}$ be any known $q$-dimensional linear matrix
family, and let an unknown $A$ be accessible only through products $Ax$ and
$A^\top y$. A recent result obtains a nearly optimal approximation from
$\mathcal L$ in about $\sqrt q$ queries, but incurs factor three and additive error
proportional to $\\|A\\|_F$. Whether sublinear query complexity can give pure
$(1+\epsilon)$ relative error was left open.

We resolve this problem with a polynomial-time, nonadaptive algorithm. For a
Frobenius-orthonormal basis $B_1,\ldots,B_q$, form the basis-invariant partial
trace $S_L=\sum_iB_iB_i^\top$. The algorithm queries the leading eigenspace
of $S_L$ exactly from the left, then fits the remaining directions from a
Gaussian right sketch. If $\lambda_j$ are the eigenvalues of $S_L$, its
constant-success query complexity is

$$\min_s\left\\\\\\{s+C\left[
 \begin{aligned}
 &\max\\\\\\{1,\lambda_{s+1}\\\\\\}\log^2(2q)\\\\
 &+\lambda_{s+1}/\epsilon
 \end{aligned}\right]\right\\\\\\}.$$

The transposed profile is also available. Since
$\lambda_{s+1}\le q/(s+1)$, every family admits pure relative error with
$\widetilde O(\sqrt{q/\epsilon})$ queries, independent of ambient dimensions
and $\\|A\\|_F/\mathrm{OPT}$. The key proof is a partial-trace covariance lemma for a
Gaussian matrix-valued design. Exact high-leverage queries make its expected
Hessian the identity, while the centered regression offset has variance only
$O(\lambda_{s+1}\mathrm{OPT}^2/k)$. A median construction amplifies success without
estimating residual norms. Finally, a symmetric Wishart lower bound for
fixed-sparsity approximation yields $\Omega(\sqrt{q/\epsilon})$ adaptive
two-sided queries when $q\epsilon$ is bounded below. Thus the universal rate
is optimal up to logarithmic factors in this joint regime. We also show that
the transformed profile gives pure relative reducible prediction risk under known
input and output covariances. For structured positive-definite precisions, it
further controls Gaussian KL error and preconditioned condition number.

## Contributions

- We give a nonadaptive, polynomial-time algorithm satisfying for every rectangular linear family. Its query complexity is
the better of two basis-invariant spectral profiles, one for each query
orientation.
- The profile implies a universal
$\widetilde O(\sqrt{q/\epsilon})$ upper bound. It has no additive error and no
dependence on the ambient dimensions or the ratio $\\|A\\|_F/\mathrm{OPT}$.
- We prove a Gaussian covariance lemma controlled by a partial trace. The
proof combines a dimension-free Schatten moment estimate, an exact
fourth-moment calculation, and matrix concentration for unbounded summands.
- We convert the adaptive symmetric Wishart lower bound of
 into
$\Omega(\sqrt{q/\epsilon})$ for general $q$-dimensional linear families when
$q\epsilon=\Omega(1)$. This matches our upper bound up to logarithms. A
separate GOE construction shows that $\Omega(1/\sqrt\epsilon)$ queries can be
necessary even for a one-dimensional family.
- We lift the theorem to covariance-weighted prediction loss without
changing its query count. For positive-definite precision matrices, the same
output controls both Gaussian KL divergence and preconditioning quality.
Circulant, Toeplitz, and known-graph precision families give explicit
dimension-adaptive profiles.

## Keywords

matrix-vector queries, relative error approximation, structured matrices, query complexity, randomized linear algebra, spectral estimation

## Files

- `main.pdf`, `supplement.pdf`
- `main.tex`, `supplement.tex`
- `references.bib`
- `aistats2027.sty`, `fancyhdr.sty`
- `main.pdf.ots`, `README_old_2026-08-19.md.ots` OpenTimestamps priority proofs

`supplement.pdf` is the current version and the one to read. `supplement_old_2026-08-19.pdf`
is the file as first published on 2026-08-10, kept only so that its OpenTimestamps
proof stays independently verifiable:

```
ots verify supplement_old_2026-08-19.pdf.ots
```

The two differ in one constant in the statement of the fixed-sparsity Wishart lower
bound quoted from Amsel et al., where the slack in the dimension range is `u` rather
than `1`. Every result is unchanged, since only the order `u/eps` is ever used.

`README_old_2026-08-19.md` is likewise the README as first published, kept for the
same reason.
