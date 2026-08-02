# Second-order Gaussian approximation for sparse Schur search

Expanding the searched Schur functional before Gaussian replacement yields a
linear field and a quadratic field throughout the full subcritical regime.  The
quadratic field separates into an off-diagonal term, whose increment is linear
in the row being replaced, and a diagonal term.  Covariance matching preserves
the mean of the diagonal term exactly, while its centered fluctuation is
smaller than the search scale.  This separation removes the one-row sparse
Gram norm that leads to the condition \(m^7=o(n)\) in a direct nonlinear
Lindeberg argument.

The construction applies to smooth functions of fixed-dimensional residual
moment matrices whose residual variances and standardized derivatives are
uniformly controlled.  It therefore treats coefficient search, partial
correlations, and conventional \(t\)-statistics through the same result.
Throughout, put

\[
m=s\log(ep/s),
\qquad
\delta=\sqrt{m/n}.
\]

## Residual Schur fields

Let \(V=(U,X)\) be a centered random vector, where
\(U\in\mathbb R^{d_U}\) has fixed dimension and \(X\in\mathbb R^p\).  The
applications below have \(d_U=2\).  From independent copies
\(V_1,\ldots,V_n\), define

\[
\Gamma=\mathbb E(VV^\top),
\qquad
\hat\Gamma=\frac1n\sum_{i=1}^n V_iV_i^\top,
\qquad
Y_i=V_iV_i^\top-\Gamma.
\]

Let \(Y_1^G,\ldots,Y_n^G\) be independent centered Gaussian symmetric
matrices with the same covariance as \(Y_i\), and put

\[
G=\frac1{\sqrt n}\sum_{i=1}^nY_i^G.
\]

Then \(G\) satisfies

\[
\operatorname{Cov}(G_{ab},G_{cd})
=\operatorname{Cov}(Y_{ab},Y_{cd}).
\]

Write \(C=\mathbb E(XX^\top)\), and let \(P_J\) project onto the range of
\(C_{JJ}\).  Every inverse below acts on this range, or equivalently is its
Moore--Penrose inverse in the original coordinates.  A symmetric direction
\(H\) is range-compatible if, for every \(|J|\le 2s\),

\[
H_{JU}=P_JH_{JU},
\qquad
H_{JJ}=P_JH_{JJ}P_J.
\]

This condition holds for every empirical row-moment direction: if
\(a\in\ker(C_{JJ})\), then \(a^\top X_J=0\) almost surely.  It also holds
for every matched Gaussian direction, because the forbidden coordinates
have zero matched variance and hence vanish almost surely.  All derivatives
and inverses below are taken on this fixed-rank affine face.

For \(S\subseteq[p]\), let

\[
R_S(A)=A_{UU}-A_{US}A_{SS}^{\dagger}A_{SU}
\]

be the residual moment matrix of \(U\) after projecting on \(X_S\).  The
searched field has the form

\[
F_{S,n}(A)=f_n\{R_S(A)\}-c_n f_n\{R_\emptyset(A)\},
\qquad |S|=s,
\]

where \(c_n\) is bounded and \(f_n\) is a scalar function on symmetric
\(d_U\times d_U\) matrices.  The empty-support subtraction allows the field to
represent a coefficient change or a studentized change from the baseline
regression.

Let \(D_U\) be the diagonal matrix of target standard deviations, assumed
invertible.  For a range-compatible \(H\), define the support norm

\[
\begin{aligned}
|H|_J
={}&\|D_U^{-1}H_{UU}D_U^{-1}\|_{\mathrm{op}}\\
&+\|C_{JJ}^{-1/2}H_{JJ}C_{JJ}^{-1/2}\|_{\mathrm{op}}
+\|C_{JJ}^{-1/2}H_{JU}D_U^{-1}\|_{\mathrm{op}},
\end{aligned}
\]

and the relative sparse norm

\[
\begin{aligned}
|H|_s=\sup_{|J|\le2s}|H|_J.
\end{aligned}
\]

All inverse square roots follow the same range convention.

The standing assumptions are the following.

- The row is sub-Gaussian relative to its second moment: for every vector
  \(a\),
  \[
  \|a^\top V\|_{\psi_2}
  \le K\{\mathbb E(a^\top V)^2\}^{1/2}
  \]
  for a fixed \(K\).
- The residual moment matrices \(R_S(\Gamma)\), \(|S|\le s\), remain in
  fixed neighborhoods \(\mathcal N_S\) on which \(f_n\) has three bounded
  derivatives after target standardization.  Define
  \[
  \kappa_s=(1+|c_n|)\max_{1\le j\le3}
  \sup_{\substack{|S|\le s,\ R\in\mathcal N_S\\
  \max_{1\le b\le j}\|D_U^{-1}Q_bD_U^{-1}\|_{\mathrm{op}}\le1}}
  \left|D^jf_n(R)[Q_1,\ldots,Q_j]\right|,
  \]
  and suppose \(0<\kappa_s<\infty\).  For a coefficient the domain condition
  is the residual-treatment variance floor.  For a partial correlation it is
  the pair of residual variance floors.  The conventional \(t\)-transform
  also requires a fixed upper bound below one on the absolute population
  partial correlations.
- Sparse empirical moment blocks concentrate in a relative norm
  \(|\cdot|_s\) satisfying
  \[
  \left\|\left|\frac1n\sum_{i=1}^n \widetilde Y_i\right|_s
  \right\|_{L_q}
  \lesssim_q\delta,
  \]
  uniformly over deterministic hybrid arrays
  \(\widetilde Y_i\in\{Y_i,Y_i^G\}\).
  The corresponding tail bound is
  \[
  \mathbb P\!\left[
  \left|\frac1n\sum_{i=1}^n\widetilde Y_i\right|_s
  >C\left\{\sqrt{\frac{m+u}{n}}+\frac{m+u}{n}\right\}
  \right]
  \le2e^{-cu},
  \qquad u\ge0,\quad m+u\lesssim n.
  \]
  The relative sub-Gaussian assumption gives both bounds by a sparse net and
  Bernstein's inequality.

The control-block component of this concentration event is exactly the
relative restricted-isometry condition used in the manuscript:

\[
\sup_{|J|\le2s}
\left\|C_{JJ}^{-1/2}\hat C_{JJ}C_{JJ}^{-1/2}-P_J\right\|_{\mathrm{op}}
\lesssim\delta,
\qquad
\hat C=\frac1n\sum_{i=1}^nX_iX_i^\top.
\]

Thus the Taylor-field argument uses the same sparse geometry that stabilizes
the original Schur search; it does not add an absolute eigenvalue condition
on \(C\).

For each support, project onto its fixed-rank face, smoothly clip the
standardized moment tuple to the preceding neighborhood, and smoothly extend
the inverse and reciprocal maps outside it.  Denote the resulting global
three-times continuously differentiable field by \(F_{S,n}^{\mathrm{loc}}\).
It agrees with \(F_{S,n}\) whenever \(|A-\Gamma|_S\) is sufficiently small
and obeys the same derivative bounds globally, with \(|A-\Gamma|_S\) clipped
at a fixed constant.

All implicit constants below depend only on the fixed target dimension, the
relative sub-Gaussian constant, the residual floors, and the fixed
localization thresholds.  Define the first-derivative scale

\[
\kappa_{1,s}
=\max_{|S|=s}\sup_{\substack{H\text{ range-compatible}\\|H|_S\le1}}
|DF_{S,n}(\Gamma)[H]|.
\]

The natural scale is

\[
a_{F,n}=\kappa_{1,s}\delta+\kappa_s\delta^2,
\qquad a_{F,n}>0.
\]

The second summand remains when the first derivative degenerates.  This
definition is homogeneous: multiplying the searched functional by a constant
multiplies \(\kappa_{1,s}\), \(\kappa_s\), and \(a_{F,n}\) by the same
constant.

The second-order Gaussian Schur field is

\[
\mathcal T^G_{n,S}
=F_{S,n}(\Gamma)
+\frac1{\sqrt n}DF_{S,n}(\Gamma)[G]
+\frac1{2n}D^2F_{S,n}(\Gamma)[G,G].
\]

For real random variables \(A,B\), write

\[
d_3(A,B)=\sup_\varphi|\mathbb E\varphi(A)-\mathbb E\varphi(B)|,
\]

where the supremum is over three-times continuously differentiable functions
with \(\max_{0\le j\le3}\|\varphi^{(j)}\|_\infty\le1\).

## Gaussian approximation

**Theorem.** Suppose the standing assumptions hold and \(m=o(n)\).  If

\[
F_*=\max_{|S|=s}F_{S,n}(\Gamma),
\]

then

\[
\begin{aligned}
d_3\!\left(
\frac{\max_{|S|=s}F_{S,n}^{\mathrm{loc}}(\hat\Gamma)-F_*}{a_{F,n}},
\frac{\max_{|S|=s}\mathcal T^G_{n,S}-F_*}{a_{F,n}}
\right)
\lesssim
\left(\frac mn\right)^{1/6}+\delta.
\end{aligned}
\]

The same bound holds with
\(\max_{|S|=s}\mathcal T^G_{n,S}\) replaced by

\[
\max_{|S|=s}F_{S,n}^{\mathrm{loc}}(\Gamma+G/\sqrt n).
\]

Moreover, sparse concentration gives
\(F_{S,n}^{\mathrm{loc}}(\hat\Gamma)=F_{S,n}(\hat\Gamma)\) simultaneously
over the supports outside an event of probability \(Ce^{-cn}\).  To see this,
take \(u=c_0n\) in the Bernstein bound, with \(c_0>0\) small enough that its
threshold lies inside the localization neighborhood.  Thus the
localized empirical field can be replaced by the original field, under any
measurable convention on the exceptional event, at an additional
\(O(e^{-cn})\) cost in \(d_3\).

If \(S^\star\) maximizes the population field, put

\[
\Delta F_{S,n}^{\mathrm{loc}}(A)
=F_{S,n}^{\mathrm{loc}}(A)-F_{S^\star,n}^{\mathrm{loc}}(A),
\qquad
\Delta\mathcal T^G_{n,S}
=\mathcal T^G_{n,S}-\mathcal T^G_{n,S^\star}.
\]

Then

\[
d_3\!\left(
\frac{\max_{|S|=s}\Delta F_{S,n}^{\mathrm{loc}}(\hat\Gamma)}{a_{F,n}},
\frac{\max_{|S|=s}\Delta\mathcal T^G_{n,S}}{a_{F,n}}
\right)
\lesssim (m/n)^{1/6}+\delta,
\]

and the same bound holds with the anchored Taylor field replaced by the
anchored localized nonlinear Gaussian field.

The proof rests on the residual representation of the first two derivatives.
That representation supplies a fixed-direction row bound with no factor of
\(s\), and it shows that the diagonal Hessian contains only one sparse
leverage factor.

## Residual derivative identities

Fix a support \(S\).  Put

\[
\ell_S^U=C_{SS}^{\dagger}\Gamma_{SU},
\qquad
w_S=U-(\ell_S^U)^\top X_S,
\qquad
R_S(\Gamma)=\mathbb E(w_Sw_S^\top).
\]

For a range-compatible direction \(H\), define its residualized blocks by

\[
H_{Sw}=H_{SU}-H_{SS}\ell_S^U
\]

and

\[
H_{ww}
=H_{UU}-H_{US}\ell_S^U-(\ell_S^U)^\top H_{SU}
+(\ell_S^U)^\top H_{SS}\ell_S^U.
\]

**Lemma 1 (Schur derivatives).** For two compatible directions \(H,Q\),

\[
DR_S(\Gamma)[H]=H_{ww}
\]

and

\[
D^2R_S(\Gamma)[H,Q]
=-H_{Sw}^\top C_{SS}^{\dagger}Q_{Sw}
-Q_{Sw}^\top C_{SS}^{\dagger}H_{Sw}.
\]

For the centered row moment \(Y=VV^\top-\Gamma\), the population normal
equations give

\[
Y_{ww}=w_Sw_S^\top-R_S(\Gamma)=:Z_S,
\qquad
Y_{Sw}=X_Sw_S^\top.
\]

Consequently,

\[
\begin{aligned}
D^2R_S(\Gamma)[H,Y]
={}&-H_{Sw}^\top C_{SS}^{\dagger}X_Sw_S^\top\\
&-w_SX_S^\top C_{SS}^{\dagger}H_{Sw},
\end{aligned}
\]

whereas the diagonal direction satisfies

\[
D^2R_S(\Gamma)[Y,Y]
=-2\bigl(X_S^\top C_{SS}^{\dagger}X_S\bigr)w_Sw_S^\top.
\]

*Proof.* Write \(D_S=A_{SU}\) and \(C_S=A_{SS}\), so that

\[
R_S(A)=A_{UU}-D_S^\top C_S^{\dagger}D_S.
\]

The calculation may be carried out after compression to the range of
\(C_{SS}\), where the inverse is ordinary.  Differentiating once and using
\(\ell_S^U=C_{SS}^{-1}\Gamma_{SU}\) gives
\(DR_S[H]=H_{ww}\).  The derivative of
\(C_S^{-1}D_S\) in direction \(Q\) is

\[
C_{SS}^{-1}(Q_{SU}-Q_{SS}\ell_S^U)
=C_{SS}^{-1}Q_{Sw}.
\]

Differentiating \(H_{ww}\) in direction \(Q\) therefore gives the displayed
bilinear Hessian.  For a row moment,

\[
\begin{aligned}
Y_{Sw}
&=X_SU^\top-\Gamma_{SU}-(X_SX_S^\top-C_{SS})\ell_S^U\\
&=X_S\{U-(\ell_S^U)^\top X_S\}^\top=X_Sw_S^\top,
\end{aligned}
\]

and the analogous expansion gives
\(Y_{ww}=w_Sw_S^\top-R_S(\Gamma)\).  Substitution
into the bilinear Hessian proves the final two identities.  \(\square\)

The chain rule turns these matrix identities into the row estimates needed
for Gaussian replacement.  With \(R_0=\Gamma_{UU}\) and
\(Z_0=UU^\top-R_0\), it gives

\[
DF_{S,n}(\Gamma)[Y]
=Df_n\{R_S(\Gamma)\}[Z_S]-c_nDf_n(R_0)[Z_0],
\]

\[
\begin{aligned}
D^2F_{S,n}(\Gamma)[H,Y]
={}&D^2f_n\{R_S(\Gamma)\}[H_{ww},Z_S]\\
&-Df_n\{R_S(\Gamma)\}\!\left[
H_{Sw}^\top C_{SS}^{\dagger}X_Sw_S^\top
+w_SX_S^\top C_{SS}^{\dagger}H_{Sw}
\right]\\
&-c_nD^2f_n(R_0)[H_{UU},Z_0],
\end{aligned}
\]

and

\[
\begin{aligned}
D^2F_{S,n}(\Gamma)[Y,Y]
={}&D^2f_n\{R_S(\Gamma)\}[Z_S,Z_S]\\
&-2\bigl(X_S^\top C_{SS}^{\dagger}X_S\bigr)
Df_n\{R_S(\Gamma)\}[w_Sw_S^\top]\\
&-c_nD^2f_n(R_0)[Z_0,Z_0].
\end{aligned}
\]

Only the middle term of the last display depends on the dimension of the
selected control space.

**Lemma 2 (intrinsic row bounds).** Let \(H\) be a range-compatible
deterministic direction, or a range-compatible random direction independent
of \(Y\).  Uniformly over \(|S|=s\),

\[
\left\|
DF_{S,n}(\Gamma)[Y]
+D^2F_{S,n}(\Gamma)[H,Y]
\right\|_{\psi_1\mid H}
\lesssim \kappa_{1,s}+\kappa_s|H|_S.
\]

For every \(q\ge2\),

\[
\left\|D^2F_{S,n}(\Gamma)[Y,Y]\right\|_{L_q}
\lesssim \kappa_s q(s+q).
\]

Both bounds hold for a covariance-matched Gaussian row \(Y^G\).  Moreover,

\[
\mathbb E D^2F_{S,n}(\Gamma)[Y,Y]
=\mathbb E D^2F_{S,n}(\Gamma)[Y^G,Y^G].
\]

*Proof.* First record the deterministic geometry behind the bounds.  Define

\[
L_S=C_{SS}^{-1/2}\Gamma_{SU}D_U^{-1}.
\]

Positive semidefiniteness of \(\Gamma\) gives \(\|L_S\|_{\mathrm{op}}\le C\),
where \(C\) depends only on \(d_U\).  In standardized coordinates,

\[
\begin{aligned}
C_{SS}^{-1/2}H_{Sw}D_U^{-1}
={}&C_{SS}^{-1/2}H_{SU}D_U^{-1}\\
&-(C_{SS}^{-1/2}H_{SS}C_{SS}^{-1/2})L_S,
\end{aligned}
\]

and the analogous four-term identity for \(H_{ww}\) yields

\[
\|C_{SS}^{-1/2}H_{Sw}D_U^{-1}\|_{\mathrm{op}}
+\|D_U^{-1}H_{ww}D_U^{-1}\|_{\mathrm{op}}
\le C|H|_S.
\]

Lemma 1 and the definition of \(\kappa_s\) consequently imply

\[
|D^2F_{S,n}(\Gamma)[H,Q]|
\le C\kappa_s|H|_S|Q|_S.
\]

We next use the dual of the support norm.  Any linear functional \(L(H)\)
of the \((U,X_S)\) blocks can be written, after standardization, as

\[
L(H)=\langle A_{UU},\bar H_{UU}\rangle
+2\langle A_{SU},\bar H_{SU}\rangle
+\langle A_{SS},\bar H_{SS}\rangle.
\]

Here \(\bar H_{UU}\), \(\bar H_{SU}\), and \(\bar H_{SS}\) are the three
standardized blocks in the definition of \(|H|_S\).

Choosing one block of \(H\) at a time along the singular vectors of the
corresponding coefficient gives

\[
\|A_{UU}\|_*+\|A_{SU}\|_*+\|A_{SS}\|_*
\le C\sup_{|H|_S\le1}|L(H)|.
\]

Apply this duality first to \(L=DF_{S,n}(\Gamma)\), whose dual norm is at
most \(\kappa_{1,s}\), and then to
\(L(Q)=D^2F_{S,n}(\Gamma)[H,Q]\), whose dual norm is at most
\(C\kappa_s|H|_S\).

Let

\[
\zeta_S=(D_U^{-1}U,C_{SS}^{-1/2}X_S).
\]

Its covariance has bounded operator norm, and it is sub-Gaussian relative
to that covariance.  Each preceding functional evaluated at
\(Y=VV^\top-\Gamma\) is a centered quadratic form
\(\zeta_S^\top A\zeta_S-\mathbb E(\zeta_S^\top A\zeta_S)\).  Spectral
decomposition and

\[
\|(a^\top\zeta_S)^2-\mathbb E(a^\top\zeta_S)^2\|_{\psi_1}
\le C\|a\|^2
\]

show that its \(\psi_1\) norm is at most \(C\|A\|_*\).  The two dual bounds
prove the first assertion, conditionally on \(H\) when \(H\) is random.

For the original-row diagonal bound, let

\[
\operatorname{lev}_S=X_S^\top C_{SS}^{\dagger}X_S.
\]

After support compression, the whitened control vector is an isotropic
sub-Gaussian vector of dimension at most \(s\), without any requirement that
its coordinates be independent.  A net of its unit sphere gives

\[
\|\operatorname{lev}_S\|_{L_q}\le C(s+q).
\]

The target residual has fixed dimension, so a quadratic residual matrix has
\(L_q\) norm \(O(q)\).  Hölder's inequality in the chain-rule display
therefore gives \(C\kappa_s\{q^2+q(s+q)\}\), which is bounded by
\(C\kappa_s q(s+q)\).

The Gaussian row needs a different argument because \(Y^G\) is not rank
one.  The first assertion follows from covariance matching: each fixed linear
functional of \(Y^G\) is centered Gaussian with variance equal to that of the
corresponding functional of \(Y\), so its \(\psi_1\) norm is bounded by the
\(L_2\) bound already obtained for the original row.  For the diagonal
assertion, set

\[
Z_S^G=DR_S(\Gamma)[Y^G],
\qquad
B_S^G=C_{SS}^{-1/2}(Y^G)_{Sw}D_U^{-1}.
\]

The entries of the fixed-dimensional Gaussian matrix
\(D_U^{-1}Z_S^GD_U^{-1}\) have bounded matched variances.  Hence its
operator norm has \(L_{2q}\) norm at most \(C\sqrt q\).  The Gaussian vector
formed from the entries of \(B_S^G\) has covariance trace at most \(Cs\),
because each entry has the variance of a standardized product of one control
and one target residual.  In particular,
\(\|\Sigma_B\|_{\mathrm{op}}\le\operatorname{tr}(\Sigma_B)\le Cs\).
Consequently, the Gaussian quadratic-form bound gives

\[
\bigl\|\|B_S^G\|_{\mathrm F}^2\bigr\|_{L_q}
\le C\{\operatorname{tr}(\Sigma_B)+q\|\Sigma_B\|_{\mathrm{op}}\}
\le Cqs.
\]

For a general direction, Lemma 1 gives

\[
D^2R_S(\Gamma)[Y^G,Y^G]
=-2(Y^G)_{Sw}^\top C_{SS}^{\dagger}(Y^G)_{Sw}.
\]

The chain rule and the last two Gaussian bounds prove
\(\|D^2F_{S,n}[Y^G,Y^G]\|_{L_q}\le C\kappa_s q(s+q)\).
Finally, the expectation of a fixed bilinear form in \(Y\) depends only on
the covariance of \(Y\), so covariance matching proves the expectation
identity.  \(\square\)

Because \(G=n^{-1/2}\sum_iY_i^G\), the Gaussian Taylor field has the exact
decomposition

\[
\begin{aligned}
\mathcal T^G_{n,S}
={}&F_{S,n}(\Gamma)
+\frac1n\sum_{i=1}^nDF_{S,n}(\Gamma)[Y_i^G]\\
&+\frac1{n^2}\sum_{i<j}D^2F_{S,n}(\Gamma)[Y_i^G,Y_j^G]
+\frac1{2n^2}\sum_{i=1}^nD^2F_{S,n}(\Gamma)[Y_i^G,Y_i^G].
\end{aligned}
\]

Replacing \(Y_i^G\) by \(Y_i\) gives the second-order empirical Taylor
field.  This identity is why the diagonal and off-diagonal quadratic terms
can be treated separately.

## The centered diagonal field

For either the original or Gaussian rows, define

\[
\mathcal D_{n,S}
=\frac1{2n^2}\sum_{i=1}^n
\left\{D^2F_{S,n}(\Gamma)[Y_i,Y_i]
-\mathbb E D^2F_{S,n}(\Gamma)[Y,Y]\right\}.
\]

**Lemma 3 (diagonal concentration).** For \(u\ge0\), put
\(\nu=(m+u)\vee2\), and suppose \(\nu\le n\).  Then

\[
\mathbb P\!\left[
\max_{|S|=s}|\mathcal D_{n,S}|
>C\left\{
\frac{\kappa_s s\sqrt \nu}{n^{3/2}}
+\frac{\kappa_s\nu(s+\nu)}{n^2}
\right\}
\right]
\le e^{-c\nu}.
\]

In particular,

\[
\mathbb E\left[
1\wedge
\frac{\max_{|S|=s}|\mathcal D_{n,S}|}{a_{F,n}}
\right]
\lesssim
\frac{s}{\sqrt{mn}}+\frac mn
\lesssim\delta.
\]

*Proof.* Lemma 2 gives, uniformly in \(S\),

\[
\left\|D^2F_{S,n}(\Gamma)[Y,Y]
-\mathbb E D^2F_{S,n}(\Gamma)[Y,Y]\right\|_{L_q}
\lesssim \kappa_s q(s+q),
\qquad q\ge2.
\]

We use the following iid sharp Rosenthal inequality.  If
\(Z_1,\ldots,Z_n\) are iid and centered and \(2\le\nu\le n\), then

\[
\left\|\sum_{i=1}^n Z_i\right\|_{L_\nu}
\lesssim
\sup_{2\le q\le \nu}
\frac \nu q\left(\frac n\nu\right)^{1/q}\|Z_1\|_{L_q}.
\]

This is the upper half of Corollary 2 in
[Latała (1997)](https://doi.org/10.1214/aop/1024404522).  For completeness,
let \(Z_i'\) be an independent copy of \(Z_i\).  Conditional Jensen gives
\(\|\sum_iZ_i\|_{L_\nu}\le\|\sum_i(Z_i-Z_i')\|_{L_\nu}\).  The differences
are iid and symmetric, so that corollary applies, and
\(\|Z_1-Z_1'\|_{L_q}\le2\|Z_1\|_{L_q}\) gives the displayed form.

Substitution of \(\|Z_1\|_{L_q}\lesssim\kappa_s q(s+q)\) reduces the
supremum, up to \(C\kappa_s\nu\), to
\((n/\nu)^{1/q}(s+q)\).  Its logarithmic derivative can change sign only
from negative to positive, so its maximum over \(2\le q\le\nu\) is attained,
up to constants, at an endpoint.  Put \(A=n/\nu\).  The \(q=2\) endpoint is
at most \(C\kappa_s s\sqrt{n\nu}\), while the \(q=\nu\) endpoint is

\[
C\kappa_s\nu A^{1/\nu}(s+\nu).
\]

If \(A^{1/\nu}\le2\), this is bounded by
\(C\kappa_s\nu(s+\nu)\).  Otherwise, writing \(b=A^{1/\nu}>2\), the elementary
bound \(\nu b\le Cb^{\nu/2}=C\sqrt A\), together with \(s\ge1\), shows that
the \(q=2\) term absorbs it.  Therefore

\[
\left\|
\sum_{i=1}^n
\{D^2F_{S,n}(\Gamma)[Y_i,Y_i]
-\mathbb E D^2F_{S,n}(\Gamma)[Y,Y]\}
\right\|_{L_\nu}
\lesssim \kappa_s\{s\sqrt{n\nu}+\nu(s+\nu)\}.
\]

Since
\(\binom ps\le e^m\) and \(\nu\ge m\), taking the maximum over the supports
costs only the factor \(\binom ps^{1/\nu}\le e\).  Markov's inequality proves
the tail bound.

The Gaussian rows satisfy the same estimate.  Because
\(a_{F,n}\ge\kappa_s\delta^2=\kappa_s m/n\)
and \(s\le m\), division by \(a_{F,n}\) gives

\[
\frac{s\sqrt m/n^{3/2}+m^2/n^2}{m/n}
=\frac{s}{\sqrt{mn}}+\frac mn
\le\delta+\delta^2.
\]

Taking the \(L_{m\vee2}\) norm of the maximum directly proves the final
claim.
\(\square\)

The expectation removed in \(\mathcal D_{n,S}\) cannot in general be
dropped.  It is a support-dependent second-order bias of size at most the
quadratic search scale, since Lemma 2 gives

\[
\max_{|S|=s}\frac1{2n}
\left|\mathbb E D^2F_{S,n}(\Gamma)[Y,Y]\right|
\le C\kappa_s\frac{s}{n}
\le C\kappa_s\delta^2.
\]

Its value is common to the empirical and Gaussian Taylor fields because the
row moments have matched covariance.

## Off-diagonal replacement

For an array \(\mathcal Y=(\mathcal Y_1,\ldots,
\mathcal Y_n)\), define the normalized off-diagonal field

\[
\begin{aligned}
\mathcal O_S(\mathcal Y)
={}&\frac{F_{S,n}(\Gamma)-F_*}{a_{F,n}}
+\frac{\mathbb E D^2F_{S,n}(\Gamma)[Y,Y]}{2na_{F,n}}\\
&+\frac1{na_{F,n}}\sum_{i=1}^nDF_{S,n}(\Gamma)[\mathcal Y_i]
+\frac1{n^2a_{F,n}}\sum_{i<j}
D^2F_{S,n}(\Gamma)[\mathcal Y_i,\mathcal Y_j].
\end{aligned}
\]

**Lemma 4 (off-diagonal invariance).** If \(m=o(n)\), then

\[
d_3\!\left(
\max_{|S|=s}\mathcal O_S(Y_1,\ldots,Y_n),
\max_{|S|=s}\mathcal O_S(Y_1^G,\ldots,Y_n^G)
\right)
\lesssim
\left(\frac mn\right)^{1/6}.
\]

*Proof.* Replace the rows one at a time.  At the \(i\)th replacement, let
\(\mathscr F_i\) be the sigma-field generated by all the other rows in the
current hybrid array, and put

\[
H_i=\frac1n\sum_{j\ne i}\widetilde Y_j
\]

be the leave-one-row hybrid average.  Conditional on \(\mathscr F_i\), the
base field, its Gibbs weights, and \(H_i\) are fixed, while either candidate
row is independent of \(\mathscr F_i\).  Inserting a row \(Y\) changes the
support value by the linear functional

\[
\Delta_{i,S}(Y)
=\frac{DF_{S,n}(\Gamma)[Y]+D^2F_{S,n}(\Gamma)[H_i,Y]}{na_{F,n}}.
\]

The original and Gaussian increment vectors have the same conditional mean
and the same full covariance matrix across supports.  Lemma 2 and
\(a_{F,n}=\kappa_{1,s}\delta+\kappa_s\delta^2\) give

\[
\frac{\kappa_{1,s}+\kappa_s|H_i|_s}{na_{F,n}}
\le
\frac{1+|H_i|_s/\delta}{n\delta}
=\frac{\Lambda_i}{\sqrt{mn}},
\]

and hence

\[
\|\Delta_{i,S}(Y)\|_{\psi_1\mid\mathscr F_i}
+\|\Delta_{i,S}(Y^G)\|_{\psi_1\mid\mathscr F_i}
\lesssim
\frac{\Lambda_i}{\sqrt{mn}},
\qquad
\Lambda_i=1+\frac{|H_i|_s}{\delta}.
\]

The same bound holds for every finite signed combination whose coefficients
have bounded total variation.  Sparse hybrid concentration gives bounded
fixed moments of \(\Lambda_i\).  It also gives the sharper estimate needed
for the Gibbs tilt: taking \(u_0=c n^{2/3}m^{1/3}\) in the hybrid Bernstein
bound yields

\[
\sum_{i=1}^n
\mathbb P\!\left\{
\Lambda_i>c(n/m)^{1/3}
\right\}
\le 2n\exp\{-c n^{2/3}m^{1/3}\}
=o\{(m/n)^{1/6}\}.
\]

Let \(\beta=\lambda m\) and smooth the maximum by

\[
\operatorname{smax}_\beta((z_S))
=\frac1\beta\log\sum_{|S|=s}e^{\beta z_S}.
\]

Since \(\log\binom ps\le m\), the smoothing error at each endpoint is at
most \(1/\lambda\).  If \(\varphi\) belongs to the defining class for \(d_3\), the
first three derivative tensors of
\(\varphi\circ\operatorname{smax}_\beta\) have total variation
bounded by

\[
C,
\qquad C(1+\beta),
\qquad C(1+\beta+\beta^2).
\]

Taylor expansion in \(\Delta_i\) through second order has matching conditional
expectations for the original and Gaussian rows.  The remainder is evaluated
at intermediate Gibbs weights.  If \(\pi_S\) denotes the Gibbs weights before
the insertion and \(\pi_S(\theta)\) the weights after inserting
\(\theta\Delta_i\), convexity
of the exponential gives, for \(k\le3\),

\[
\prod_{a=1}^k\pi_{S_a}(\theta)
\le
\prod_{a=1}^k\pi_{S_a}
\exp\!\left[
\theta\beta\left\{
\sum_{a=1}^k\Delta_{i,S_a}
-k\sum_T\pi_T\Delta_{i,T}
\right\}
\right].
\]

The random variable in braces is a centered signed combination with
conditional \(\psi_1\) norm at most \(C_k\Lambda_i/\sqrt{mn}\).  On
\(\Lambda_i\le c(n/m)^{1/3}\), the choice

\[
\lambda=(n/m)^{1/6}
\]

makes its exponential moment uniformly bounded because

\[
\frac{\beta\Lambda_i}{\sqrt{mn}}
=\lambda\sqrt{m/n}\,\Lambda_i\le c.
\]

Conditional Hölder inequalities and Lemma 2 then bound the one-row Taylor
remainder by

\[
C(1+\beta+\beta^2)
\frac{\Lambda_i^3}{(mn)^{3/2}}.
\]

The complement of
\(\{\Lambda_i\le c(n/m)^{1/3}\}\) contributes at most the explicit
Bernstein probability above because the test functions are bounded.
Summing the \(n\) replacements and adding the two smoothing errors gives

\[
\frac1\lambda
+\frac1{m^{3/2}\sqrt n}
+\frac{\lambda}{\sqrt{mn}}
+\lambda^2\sqrt{m/n}
+o\{(m/n)^{1/6}\}.
\]

For \(\lambda=(n/m)^{1/6}\), both \(1/\lambda\) and
\(\lambda^2\sqrt{m/n}\) equal \((m/n)^{1/6}\), while the other displayed
terms are smaller.  This proves the lemma.  \(\square\)

## Proof of the theorem

For a range-compatible perturbation \(H\) with \(|H|_s\) sufficiently small,
the residual floors and bounded third derivatives give the uniform expansion

\[
\max_{|S|=s}
\left|
F_{S,n}(\Gamma+H)-F_{S,n}(\Gamma)
-DF_{S,n}(\Gamma)[H]
-\frac12D^2F_{S,n}(\Gamma)[H,H]
\right|
\lesssim \kappa_s|H|_s^3.
\]

Let \(\mathcal E\) be the event that both endpoint perturbations lie in this
neighborhood.  Taking \(u=c_0n\) in the hybrid Bernstein bound, with \(c_0\)
fixed and sufficiently small, gives
\(\mathbb P(\mathcal E^c)\le Ce^{-cn}\), while its fixed-moment form gives
\(\mathbb E|H|_s^3\le C\delta^3\) at either endpoint.  Since
\(a_{F,n}\ge\kappa_s\delta^2\), the normalized Taylor error is
\(O(\delta)\)
in truncated \(L_1\) on \(\mathcal E\); bounded \(d_3\) test functions absorb
\(\mathcal E^c\).  Lemma 3 removes the centered diagonal part of each Taylor
field at the same cost.  The retained diagonal expectation is identical at
the two endpoints.  Lemma 4 compares the remaining off-diagonal fields with
error \(O\{(m/n)^{1/6}\}\).  The triangle inequality proves the first
assertion.

The same argument for
\(F_{S,n}^{\mathrm{loc}}(\Gamma+G/\sqrt n)\) shows that the nonlinear
Gaussian field and \(\mathcal T^G_{n,S}\) differ by \(O(\delta)\) after
normalization.  Subtracting a fixed support changes each derivative and
diagonal bound by at most a constant factor, which proves the anchored
version.  \(\square\)

## Regression specializations

For coefficient search, let

\[
\beta_\emptyset^*=\frac{\mathbb E(xy)}{\mathbb E(x^2)},
\qquad
r=y-\beta_\emptyset^*x.
\]

Then \(\mathbb E(xr)=0\).  Take \(U=(x,r)\) and

\[
f_n(R)=\frac{R_{12}}{R_{11}},
\qquad c_n=1.
\]

Let

\[
\sigma_0^2=\mathbb E(x^2),
\qquad
\sigma_r^2=\mathbb E(r^2),
\qquad
d=\mathbb E(Xx),
\qquad
h=\mathbb E(Xr).
\]

Define

\[
\|z\|_{C,k}
=\sup_{|J|\le k}(z_J^\top C_{JJ}^{\dagger}z_J)^{1/2},
\qquad
\phi_k=\frac{\|d\|_{C,k}^2}{\sigma_0^2},
\qquad
\widetilde\Psi_k=\|h\|_{C,k}.
\]

Then the first-derivative envelope is bounded by

\[
\kappa_{1,s}
\lesssim
\frac1{\sigma_0}
\{\sigma_r\sqrt{\phi_s}+\widetilde\Psi_s\}.
\]

The overlap floor permits \(\kappa_s=C\sigma_r/\sigma_0\).  Thus the
manuscript's coefficient scale is the convenient upper scale

\[
a_n
=\frac1{\sigma_0}
\left[
\{\sigma_r\sqrt{\phi_s}+\widetilde\Psi_s\}\delta
+\sigma_r\delta^2
\right].
\]

Because \(a_{F,n}\lesssim a_n\), the theorem remains valid under
normalization by \(a_n\), with only a constant adjustment in the \(d_3\)
bound.  It gives the observational matched-moment approximation under
\(m=o(n)\), without sparse treatment alignment.

For partial correlations, take \(U=(x,y)\) and

\[
f_n(R)=\frac{R_{12}}{(R_{11}R_{22})^{1/2}},
\qquad
c_n=\sqrt{\frac{n-1}{n-s-1}}.
\]

Write \(\Gamma_y\) and \(\hat\Gamma_y\) for the corresponding population
and empirical moments, and put

\[
\tau_S(A)=f_n\{R_S(A)\},
\qquad
\hat t_{0,S}=\sqrt{n-s-1}\,\tau_S(\hat\Gamma_y),
\qquad
\hat t_{0,\emptyset}=\sqrt{n-1}\,\tau_\emptyset(\hat\Gamma_y).
\]

Uniform lower bounds on the treatment and outcome residual variances keep the
standardized curvature scale bounded.  Let \(|\cdot|_{y,S}\) denote the
support norm with target \((x,y)\).  With

\[
\kappa_{1,t,s}
=\max_{|S|=s}\sup_{\substack{H\text{ range-compatible}\\|H|_{y,S}\le1}}
|DF_{S,n}(\Gamma)[H]|,
\qquad
a_{t,n}=\kappa_{1,t,s}\delta+\delta^2,
\]

the same theorem gives the matched-moment approximation for the
partial-correlation contrast under \(m=o(n)\).  Multiplication by
\(\sqrt{n-s-1}\) identifies it with

\[
\hat t_{0,S}-\hat t_{0,\emptyset}
=\sqrt{n-s-1}
\{\tau_S(\hat\Gamma_y)-c_n\tau_\emptyset(\hat\Gamma_y)\}.
\]

For conventional \(t\)-statistics, replace \(f_n\) by

\[
f_n(R)
=\frac{R_{12}}
{\{R_{11}R_{22}-R_{12}^2\}^{1/2}}.
\]

In addition to the two residual variance floors, assume

\[
\sup_{|S|\le s}|\tau_S(\Gamma_y)|\le1-c_\tau
\]

for a fixed \(c_\tau>0\).  This bounds the standardized derivatives of the
transformation.  The exact statistic is

\[
\hat t^{\mathrm{LS}}_{0,S}
=\sqrt{n-\operatorname{rank}(X_S)-1}\,
f_n\{R_S(\hat\Gamma_y)\}.
\]

Here \(\operatorname{rank}(X_S)\) denotes the rank of the sampled control
matrix.  If every searched control block has rank \(s\), then

\[
\hat t^{\mathrm{LS}}_{0,S}-\hat t^{\mathrm{LS}}_{0,\emptyset}
=\sqrt{n-s-1}\left[
f_n\{R_S(\hat\Gamma_y)\}-c_nf_n\{R_\emptyset(\hat\Gamma_y)\}
\right].
\]

Full rank is needed only for this common degrees-of-freedom factor; it is not
needed for the Gaussian approximation to the Schur field itself.

## Reduction to score products

The second-order field is a quadratic polynomial in \(G\).  Its constant,
linear, off-diagonal quadratic, and diagonal-mean terms retain, respectively,
the population landscape, the Gaussian influence process, the quadratic
moment interaction, and the support-dependent second-order bias.  It remains
equivalent to the nonlinear Gaussian moment field in the subcritical regime.

The score-product and greedy results require their own geometric hypotheses.
In the coefficient specialization, sparse treatment alignment is

\[
\sqrt{\phi_{2s}}\lesssim\delta.
\]

Combining the present theorem with the manuscript's score-reduction result
then gives the matched score-product field at the sharper scale.  The
covariance-aware forward rule applies to that field.  A static coordinatewise
top-\(s\) sort requires in addition local isotropy,

\[
\rho_s(C)
=\sup_{|J|\le2s}\|C_{JJ}-I\|_{\mathrm{op}}=o(1).
\]

Thus the sequence of reductions is

\[
\begin{aligned}
\text{empirical Schur search}
&\longrightarrow
\text{matched second-order Gaussian Schur field}\\
&\longrightarrow
\text{matched score products under sparse treatment alignment}\\
&\longrightarrow
\text{forward conditional products, or top-\(s\) under local isotropy}.
\end{aligned}
\]

The first approximation requires \(m=o(n)\), matching the score replacement.
Applying Lindeberg replacement directly to the nonlinear field instead takes
a supremum sparse norm of each rank-one row before smoothing the maximum and
produces the stronger sufficient condition \(m^7=o(n)\).  The Taylor split
removes that loss.
