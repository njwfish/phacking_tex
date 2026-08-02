# Specification search for IPW and AIPW estimators

This directory develops the follow-up theory for specification search with
estimated propensity and outcome models.  The note begins with a uniform
support-indexed M-estimation expansion and then specializes it to logistic IPW
and AIPW estimators with logistic propensity and linear outcome models.

Build the note from the repository root with

```sh
latexmk -norc -pdf -outdir=ipw_aipw_followup/build \
  ipw_aipw_followup/ipw_aipw_m_estimation.tex
```
