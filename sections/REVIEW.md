# polish-prose review — Contrast paragraph (post-selection inference + the tension)

One merged paragraph under `\paragraph{Contrast with post-selection inference and the validity--sharpness tension.}`. Berk cited once; A-5 (the ex-post-credibility plug-in) cut; the conclusion now pushes a **sensitivity-analysis** logic over finite-population guarantees, pointing to the discussion. Four sentences.

| Code | Sentence | Feedback / rewrite |
|------|----------|--------------------|
| A-1 | The issue of evaluating an ensemble of available models in a given study has also been approached, from a different side, by post-selection inference, which seeks not to characterise or detect questionable practices but to build sequentially valid decisions across the selection \citep{cox1975dataSplitting,fithian2014optimal,lee2016exact,tianTaylor2018selective,kuchibhotlaKolassaKuffner2022postSelection,chengSpectorJanson2025chiseling}. | |
| A-2 | For the choice of control variables studied here, \citet{berk2013valid} provide such a guarantee, valid against every selection rule. | |
| A-3 | In this case, the guarantee seems to come at a heavy price, since, with no structure assumed of the design, the correction counts the candidate submodels as if their directions were unstructured on the sphere, when the adjustment sets are in fact highly dependent; the present results make this conservatism precise once the controls are genuinely correlated. | |
| A-4 | While the methods developed here, resting on concentration-of-measure phenomena, are unlikely to deliver the exact, finite-population guarantees that post-selection inference draws from multiple testing, their descriptive gain can still be turned into methodological insight, in the form of a sensitivity analysis rather than a valid test (Section~\ref{sec:discussion}). | |

---

**General observations:**

- **A-5 cut**, per your note; the paragraph now closes on A-4.
- **A-4 reframed** to your sensitivity-analysis conclusion: methods built on concentration-of-measure are unlikely to give the exact, finite-population (multiple-testing-style) guarantees, but the descriptive gain converts into methodological insight "in the form of a sensitivity analysis rather than a valid test." Ends with a placeholder pointer `Section~\ref{sec:discussion}` — on `implement` I'll add `\label{sec:discussion}` to the (currently stub) discussion section so the reference resolves.
- **A-3** takes your reworded opening ("the guarantee seems to come at a heavy price, since, with no structure assumed of the design…"); I swapped your second "this" for "the guarantee" to avoid "In this case, this…", and closed on a clean clause instead of the old "far heavier… warrant."

---

**Feedback (write `implement` to apply, or list per-sentence changes below):**
