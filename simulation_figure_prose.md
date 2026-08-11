# Proposed prose for the simulation figures

This file collects self-contained LaTeX blocks for insertion into the manuscript.
Each destination gives the literal line before the insertion pass and the line
reached when the prose and figure blocks below are inserted in order, with one
blank line after each block. The figure paths point to the current draft PDFs.
The quoted source anchors remain authoritative if either the prose or the figures
change.

## 1. Introduction: the geometric organization

**Destination:** `sections/introduction.tex:56` (sequential line 56). Insert
before ``To summarize, our mathematical derivations hold,'' immediately after
the paragraph that defines coordinate search through
`\sup_{S \subseteq [p], |S|=s} \hat\beta_{0,S}`.

```latex
The simulations are organized around the quantities that enter the coordinate
search bounds. Under randomization, these are the size of the search problem
and the share of outcome variation that a size-$s$ specification can explain.
We first vary them separately through $n$, $p$, and the distribution of
prognostic signal across the controls, and then vary the orientation of that
signal relative to the control covariance. In the observational case, the
admissible specifications can also have different population coefficients, so
population drift becomes an additional source of displacement. This sequence
traces each feature of the simulations to a corresponding term in the bounds.
```

## 2. Experimental case: available controls and prognostic concentration

**Destination:** `sections/bounds.tex:195` (sequential line 195). Insert before
``The theorem is to be compared with the scale of a single fixed
configuration,'' after the paragraph ending ``the first term takes over.''

```latex
Figure~\ref{fig:randomized-coordinate-geometry} is designed to establish a
clear interpretation of $\theta_s$ in a simple simulation setting. We
randomize the treatment
$T^{(i)}=x_0^{(i)} \sim \operatorname{Bern}(1/2)$, fixing $s$ and
$\sigma_\varepsilon^2$, and vary the number $p$ of available controls
$X^{(i)}=X_{-0}^{(i)} \sim \mathcal{N}(0,I_p)$ and the sample size $n$. The
treatment has no effect on the outcome, $\beta_0=0$. The key additional idea
is the number $k$ of ``prognostic controls'' that actually carry signal for
the outcome.

The $k$ nonzero coordinates of $\beta_{-0}$ have equal magnitude and are
rescaled as $k$ varies so that $\norm{\beta_{-0}}_2^2$ remains fixed. For
$k>0$, this gives
\begin{equation*}
        \theta_s
        =
        \frac{\norm{\beta_{-0}}_2^2}
        {\norm{\beta_{-0}}_2^2+\sigma_\varepsilon^2}
        \min\left\{1,\frac{s}{k}\right\},
\end{equation*}
while $k=0$ gives $\theta_s=0$. For $p\ge k$, increasing $p$ at fixed $k$
changes $\delta_{s,n,p}$ without changing $\theta_s$; increasing $k$ at fixed
$p$ spreads the same outcome signal over more controls and lowers $\theta_s$;
increasing $n$ lowers $\delta_{s,n,p}$ without changing $\theta_s$.

For each design, we begin with the no-control coefficient
$\hat\beta_{0,\emptyset}$ and add the control that produces the largest current
value of $|\hat\beta_{0,S}|$ until exactly $s$ controls have been selected. The
figure reports the resulting mean change in coefficient magnitude. This
forward search is an attainable counterpart to the two-sided version of the
coordinate maximum in \eqref{eq:searched-sup}. Applying
\eqref{eq:experimental-matching} to $y$ and $-y$ gives the same search scale,
which is of order
$\delta_{s,n,p}^2$ when $\theta_s=0$ and of order
$\delta_{s,n,p}\sqrt{\theta_s}$ when the prognostic term dominates. The panels
show these two regimes directly: enlarging the menu makes larger displacements
available, concentrating a fixed prognostic signal raises the scale further,
and increasing $n$ drives both coefficient displacements toward zero at their
respective rates.
```

**Figure draft:**

```latex
\begin{figure}[t]
\centering
\includegraphics[width=.49\linewidth]{figures/simulations/coefficient-randomized-menu-size.pdf}\hfill
\includegraphics[width=.49\linewidth]{figures/simulations/coefficient-randomized-prognostic-share.pdf}
\par\medskip
\includegraphics[width=.49\linewidth]{figures/simulations/coefficient-randomized-sample-size.pdf}
\caption{Coordinate search under randomization. The treatment
$T^{(i)}=x_0^{(i)} \sim \operatorname{Bern}(1/2)$ is independent of
$X^{(i)}=X_{-0}^{(i)} \sim \mathcal{N}(0,I_p)$ and has no effect on the outcome.
The panels vary the number $p$ of
available controls (top left), the prognostic share $k/p$ (top right), and the
sample size $n$ (bottom), while holding $s$, $\sigma_\varepsilon^2$, and the total
prognostic signal fixed. The ordinate is the Monte Carlo mean of
$|\hat\beta_{0,\widehat S}|-|\hat\beta_{0,\emptyset}|$, where forward search
selects exactly $s$ controls. Increasing $k$ lowers $\theta_s$ by spreading the
same signal across more coordinates. When a labelled value of $k$ exceeds $p$,
all $p$ controls are prognostic, so that curve coincides with the dense design.
At $p=s$, the reported specification is fixed and there is no coordinate
choice.}
\label{fig:randomized-coordinate-geometry}
\end{figure}
```

## 3. Experimental case: covariance orientation

**Destination:** `sections/bounds.tex:195` before the insertion pass (sequential
line 257). Insert after the preceding prose and
Figure~`\ref{fig:randomized-coordinate-geometry}` blocks, but still before ``The
theorem is to be compared with the scale of a single fixed configuration.''

```latex
Figure~\ref{fig:covariance-prognostic-geometry} asks how covariance changes the
same prognostic structure. We now fix $n$, $p$, $s$, $k$, and the total outcome
variance, but replace $I_p$ with a covariance matrix containing a rank-one
component of strength $\rho$. For each value of $\rho$, the covariance spectrum
is fixed while its leading direction is rotated. At alignment $a=0$, this
direction is supported on the $k$ prognostic controls; at $a=1$, it is spread
equally across all $p$ controls.

This rotation leaves the total prognostic signal and the eigenvalues of $C$
unchanged, but it changes $C\beta_{-0}$ and therefore $\Psi_s$ and $\theta_s$.
The left panel summarizes the redistribution by the participation ratio of the
squared marginal outcome correlations, which is the effective number of
prognostic controls. The right panel reports the corresponding coefficient
gain. As $a$ increases, correlation first creates additional prognostic proxies
and then makes those proxies increasingly redundant, producing the observed
nonmonotonicity. Covariance therefore matters through the sparse outcome
variation it makes accessible, not through the overall strength of dependence
alone: designs with the same covariance eigenvalues can have different values
of $\theta_s$ and different susceptibility to coordinate search.
```

**Figure draft:**

```latex
\begin{figure}[t]
\centering
\includegraphics[width=.49\linewidth]{figures/simulations/effective-prognostic-dimension.pdf}\hfill
\includegraphics[width=.49\linewidth]{figures/simulations/coefficient-covariance-alignment.pdf}
\caption{Covariance orientation and prognostic concentration. For each
rank-one covariance strength $\rho$, the covariance spectrum, total outcome
variance, $n$, $p$, and $s$ remain fixed while the leading covariance direction
rotates from the $k$ prognostic controls ($a=0$) toward the dense direction
($a=1$). The left panel reports the effective number of prognostic controls;
the right reports the mean increase in $|\hat\beta|$ attained by forward
coordinate search. The path separates the creation of prognostic proxies from
their eventual redundancy.}
\label{fig:covariance-prognostic-geometry}
\end{figure}
```

## 4. Observational case: population drift

**Destination:** `sections/bounds.tex:341` before the insertion pass (sequential
line 438). Insert before
`\subsection{The t-Statistic and Consequences for Replicability}`, after the
paragraph ending ``more accurately described by the lower bound.''

```latex
Figure~\ref{fig:observational-coordinate-geometry} introduces the population
drift that arises when $d \ne 0$. The treatment remains Bernoulli, but its
assignment probability depends on a score constructed from the controls. We
index the strength of this dependence by
$R_T^2=d^\top C^{-1}d/\sigma_0^2$, the population share of treatment variance
explained by the controls, and vary $R_T^2$ together with $n$. The treatment
score is orthogonal to the prognostic score, so the no-control coefficient has
no population omitted-variable bias.

Specification search need not preserve this orthogonality. A balanced set of
controls does, while an unbalanced set creates a nonzero drift $b(S)$. At the
randomized endpoint $R_T^2=0$, every specification has the same
population coefficient and the searched displacement vanishes with $n$. For
any fixed positive $R_T^2$, the process $\{\beta_{0,S}^\star\}$ has different
centers across supports, and the searched coefficient converges toward the
largest of them. The nonzero limit approached by each confounded curve is
therefore the population drift component of the observational bound.
```

**Figure draft:**

```latex
\begin{figure}[t]
\centering
\includegraphics[width=.72\linewidth]{figures/simulations/coefficient-confounding-sample-size.pdf}
\caption{Coordinate search when the treatment is correlated with the controls.
The figure varies $n$ and the explained treatment share
$R_T^2=d^\top C^{-1}d/\sigma_0^2$. The treatment and prognostic scores are
orthogonal without adjustment, but an unbalanced size-$s$ specification creates
a nonzero $b(S)$. The ordinate is the mean change in $|\hat\beta|$ attained by
exhaustive search over the size-$s$ specifications. Under randomization this
change vanishes with $n$; for fixed positive $R_T^2$, it approaches the
population drift available through specification choice.}
\label{fig:observational-coordinate-geometry}
\end{figure}
```

## 5. Searched significance

**Destination:** append at `sections/bounds.tex:465` before the insertion pass
(sequential line 594). Insert after the paragraph ending ``the $\sqrt n$ budget
binds instead.'' The four simulation comments currently at lines 461--464 may
remain immediately above this block.

```latex
Figure~\ref{fig:tstat-coordinate-search} asks what the preceding coefficient
scales imply for a nominal two-sided $5\%$ test of $\beta_0=0$. We use the same
simulation designs, but now search for the largest
$|\hat t_{0,S}|$ over specifications with exactly $s$ controls. Under
randomization, Theorem~\ref{thm:tstat} gives the search scale
\begin{equation*}
        \sqrt{s\log(ep/s)}
        \sqrt{\theta_s+\delta_{s,n,p}^2}.
\end{equation*}
This expression makes the sample-size comparison immediate. When
$\theta_s=0$, the search contribution is of order
$s\log(ep/s)/\sqrt n$ and vanishes. When $\theta_s$ remains positive, it is of
order $\sqrt{s\log(ep/s)\theta_s}$ and does not vanish at fixed $p$ and $s$.
The coefficient displacement still converges to zero in both cases, but with
prognostic controls it does so on the same $n^{-1/2}$ scale as the standard
error. The false-rejection probability can therefore remain above $5\%$ even
in an arbitrarily large randomized experiment.

The available-control panel shows the complementary role of $p$. At $p=s$
there is only one admissible size-$s$ specification, so rejection is at its
nominal level. Increasing $p$ expands the search menu and raises rejection,
with the largest increase occurring when a small set of controls carries a
fixed share $\theta_s$ of the outcome variation. Although
Theorem~\ref{thm:tstat} is stated for a one-sided supremum, applying it to $y$
and $-y$ gives the same rate for the two-sided search used here.

The confounded curves describe a different regime. For each positive
$R_T^2=d^\top C^{-1}d/\sigma_0^2$, the maximal population partial correlation
is held away from zero, so Assumption~\ref{ass:testing}(i) does not hold. The
selected $t$-statistic then grows at the $\sqrt n$ rate and rejection tends
toward one. These curves show the signal-dominated observational behavior that
lies outside the local testing regime.
```

**Figure draft:**

```latex
\begin{figure}[t]
\centering
\includegraphics[width=.49\linewidth]{figures/simulations/rejection-randomized-menu-size.pdf}\hfill
\includegraphics[width=.49\linewidth]{figures/simulations/rejection-confounding-sample-size.pdf}
\caption{False rejection after coordinate search. Both panels report rejection
of a nominal two-sided $5\%$ test after maximizing $|\hat t_{0,S}|$ over
specifications with exactly $s$ controls. The left panel uses forward search
and varies $p$, beginning at the fixed-specification endpoint $p=s$. The right
panel enumerates all size-$s$ specifications and varies $n$ under randomization
and fixed values of $R_T^2$. Without prognostic signal, randomized rejection
returns to $5\%$ as $n$ grows; with $\theta_s>0$, it remains elevated even
though the coefficient displacement vanishes. Fixed positive $R_T^2$ produces
the signal-dominated observational contrast.}
\label{fig:tstat-coordinate-search}
\end{figure}
```

## 6. Matched semisynthetic sensitivity

**Destination:** append at `sections/bounds.tex:465` before the insertion pass
(sequential line 643). Insert after the preceding prose and
Figure~`\ref{fig:tstat-coordinate-search}` blocks. This remains conditional on
retaining the semisynthetic comparison in the main text; it must precede
`sections/plugin_approximation.tex`, which is included next by `main.tex`.

```latex
Figure~\ref{fig:semisynthetic-coordinate-geometry} extends the same design to
empirical control covariances. We take the control matrices from the callback
and hurricane datasets, but generate new treatments and outcomes. In both
datasets we use the same $n$, $p$, $s$, and treatment rate. The observed
controls determine $C$ and a prognostic score;
the outcome is calibrated to a chosen full-control explained share $R_Y^2$,
and the Bernoulli assignment probabilities are calibrated to a chosen
full-control explained share $R_T^2$.

The two panels evaluate the same grid of $(R_T^2,R_Y^2)$ values. The vertical
axis controls how strongly the controls predict the outcome, and the horizontal
axis moves the design from random assignment toward stronger treatment--control
dependence. Both axes are full-control summaries, whereas the bounds depend on
sparse quantities. In particular, $R_Y^2$ does not determine the sparse
explained share $\theta_s$, and $R_T^2$ does not determine the
support-dependent drift $b(S)$. The empirical covariance and the orientation
of the prognostic score determine how much of each full-control association a
size-$s$ search can use.

The surfaces therefore provide a matched comparison rather than a reanalysis
of either empirical effect. Any difference between the callback and hurricane
panels at the same $(R_T^2,R_Y^2)$ point is caused by control geometry that
these two scalar shares do not record. The synthetic axes remain informative,
but a study-specific assessment of hackability also requires the observed
covariance and prognostic direction.
```

**Figure draft:**

```latex
\begin{figure}[t]
\centering
\includegraphics[width=.49\linewidth]{figures/simulations/coefficient-callbacks-sensitivity.pdf}\hfill
\includegraphics[width=.49\linewidth]{figures/simulations/coefficient-hurricanes-sensitivity.pdf}
\caption{Matched semisynthetic sensitivity. The callback (left) and hurricane
(right) panels use the same $n$, $p$, $s$, Bernoulli treatment rate, and grid of
full-control explained shares $(R_T^2,R_Y^2)$. Each dataset supplies its
empirical control covariance and a prognostic direction; treatment and outcome
are generated semisynthetically. Color records the mean increase in
$|\hat\beta|$ attained by forward coordinate search on a common scale. A
difference between panels at the same grid point reflects covariance and
prognostic geometry not summarized by $(R_T^2,R_Y^2)$.}
\label{fig:semisynthetic-coordinate-geometry}
\end{figure}
```

## 7. Common appendix bridge for the computational search

**Destination:** `sections/appendix.tex:3`. Insert a new simulation-design
section before the current `\section{Proofs of the Bounds}` and place this
paragraph in that section. It is not needed if the first main-text figure
caption retains the complete forward-search description.

```latex
Exhaustive enumeration of the coordinate search class is infeasible at the
dimensions used in the main simulations, so those experiments use forward
search. Starting from the no-control regression, the procedure adds the control
whose inclusion maximizes the current objective and continues until exactly
$s$ controls have been selected. The coefficient experiments maximize the
absolute treatment coefficient, while the testing experiments maximize the
absolute treatment $t$-statistic. Exhaustive enumeration at smaller dimensions
measures the gap between this attainable search and the coordinate supremum.
Figure~\ref{fig:greedy-exact-search} reports this audit for the two-sided
testing objective.
```

**Figure draft:**

```latex
\begin{figure}[t]
\centering
\includegraphics[width=.72\linewidth]{figures/simulations/greedy-exact-search-audit.pdf}
\caption{Forward search against exhaustive enumeration. The figure compares
false-rejection probabilities after forward and exhaustive search for the
largest absolute treatment $t$-statistic. The diagonal denotes equality.}
\label{fig:greedy-exact-search}
\end{figure}
```
