# research-polish-prose review — the paragraphs after Theorem 1 (§2.2), round 6

B-1 now just names the two terms, with no inequality and no threshold display. B-2 is the abundant-data case, B-3 the few-contributing-controls case written through $\|\beta_{-0}\|_0$. C-1 compares with one fixed configuration and the equation drops the approximation sign. C-2 takes your wording. Seven sentences and one equation.

| Code | Sentence                                                                                                                                                                                                                                                                                      | Feedback / rewrite |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ |
| A-1  | To begin with, the theorem states that the displacement covariate search can buy depends primarily on$\delta_{s,n,p}$, the square root of the share of the sample that the search spends.                                                                                                   |                    |
| A-2  | More specifically, at a fixed budget$s$ that share vanishes with the sample and so does the displacement, at rate $\log p / n$ when no small group of controls predicts the outcome and at worst $\sqrt{\log p / n}$ when some do, so the reported coefficient converges on the effect. |                    |
| A-3  | That the number of covariates the analyst may consult enters only through$\log p$ is a first finding of this work, since what governs the displacement is how many controls are reported and hardly how many were available.                                                                |                    |
| A-4  | On the other hand, as$s$ grows to the scale of the sample, the setting in which a researcher has as many admissible specifications as observations, the share is of order one and so is the displacement, which then reaches the scale of $\beta_0$ itself.                               |                    |

| Code | Sentence                                                                                                                                                                                                                                                                   | Feedback / rewrite |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ |
| B-1  | The bound depends on two terms,$\delta_{s,n,p}^2 \sqrt{\beta_{-0}^\top C \beta_{-0} + \sigma_\varepsilon^2}/\sigma_0$ and $\delta_{s,n,p} \Psi_s / \sigma_0$.                                                                                                          |                    |
| B-2  | When data are abundant and the budget$s$ is small, $\delta_{s,n,p}$ is small and the term in $\Psi_s$ is the larger of the two.                                                                                                                                      |                    |
| B-3  | When few controls actually contribute, however,$\Psi_s$ stops growing once $s$ passes $\|\beta_{-0}\|_0$, being pinned at $\sqrt{\beta_{-0}^\top C \beta_{-0}}$ from there on while $\delta_{s,n,p}$ keeps rising with the budget, so the first term takes over. |                    |

| Code | Sentence                                                                      | Feedback / rewrite |
| ---- | ----------------------------------------------------------------------------- | ------------------ |
| C-1  | The theorem is to be compared with the scale of a single fixed configuration, |                    |

$$
\Var\big(\hat\beta_{0,S}\big) \;\asymp\; \frac{\beta_{-0}^\top C \beta_{-0} + \sigma_\varepsilon^2}{n\, \sigma_0^2}\,.
$$

| Code | Sentence                                                                                                                                                                                                                                                                         | Feedback / rewrite                                                              |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| C-2  | The relative displacement is then worth up to$\sqrt{s\log(ep/s)}$, which does not decay even at a fixed budget, and while it stays small against the effect $\beta_0$ itself, it is what becomes problematic for hypothesis testing, the subject of Section~\ref{sec:tstat}. | use the expression "true effect size beta0", and "this will become problematic" |

---

**General observations:**

- **B-3 is exact, not approximate.** If $J$ contains the support of $\beta_{-0}$ then $X_{-0}\beta_{-0}$ lies in $\operatorname{span}(X_J)$, so the explained variance is the whole of $\beta_{-0}^\top C \beta_{-0}$. Hence $\Psi_s = \sqrt{\beta_{-0}^\top C \beta_{-0}}$ for every $s \ge \|\beta_{-0}\|_0$, and the budget buys nothing more on that side while it keeps raising $\delta_{s,n,p}$. That is the mechanism B-3 states.
- **On the approximation sign in C.** The variance of a fixed configuration is $(\beta_{-0}^\top C \beta_{-0} + \sigma_\varepsilon^2 - \text{what } S \text{ explains})/(n\sigma_0^2)$, so an equality would need the explained part carried along and an inequality would need care at finite $n$. The $\asymp$ above says it is of that order, which is all C-2 uses. If you would rather have no relation symbol at all, C-1 can read "has variance of order" and the display becomes the right-hand side alone.
- B-1 no longer says which term is larger, so B-2 and B-3 carry that entirely, one case each. The threshold that decided it, $\Psi_s$ against $\delta_{s,n,p}\sqrt{\beta_{-0}^\top C \beta_{-0} + \sigma_\varepsilon^2}$, is now implicit; it is what both sentences are instances of.

---

**Feedback (write `implement` to apply, or list per-sentence changes below):**
