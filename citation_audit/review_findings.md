# Citation Review Findings

Review completed with six subagents against the local source archive in
`sources/`. The current post-edit audit table is
`citation_audit/citation_contexts.tsv`.

Summary after integration:

- Citation contexts reviewed: 84
- Unique active citation keys: 65
- Introduction citation contexts reviewed: 13
- Current supported citation contexts: 84
- Current weak/mismatch/metadata rows: 0

## Integration Fixes

- Moved `head2015extent` out of the introduction's methodological-foundations
  list and into the field-level diagnostics sentence.
- Split the introduction's field-level evidence sentence from the econometric
  diagnostics/methods sentence, so `andrews2019identification` and
  `elliott2022detecting` no longer carry a prevalence claim.
- Reworded the literature-review p-value diagnostics sentence so
  `brunsIoannidis2016pcurve` supports p-curve diagnostics rather than an
  unqualified prevalence claim.
- Added the exact AER `salaimartin1997twoMillion` PDF as
  `sources/salaimartin1997twoMillion/paper.pdf`; retained the related NBER
  working-paper PDF as an alternate artifact.
- Reworded the preregistration and pre-analysis-plan paragraph to distinguish
  pre-analysis-plan constraints from broader models of scientific
  communication, transparency, p-hacking incentives, and implementable
  statistical decisions.
- Reworded the observational-control sentence so `kingDetectingModelDependence2007`
  supports model dependence specifically, and moved `cinelliForneyPearl2022crash`
  to the good/bad-controls context.
- Split ordinary omitted-variable-bias sensitivity citations from the
  instrumental-variables sensitivity extension `cinelliHazlett2025iv`.
- Narrowed the experimental-case restricted-eigenvalue claim from correlated
  subgaussian designs to correlated Gaussian designs for
  `raskuttiWainwrightYu2010restricted`.

## Reviewer Batches

- Batch A reviewed introduction methodological-foundation citations.
- Batch B reviewed introduction field-level diagnostic citations.
- Batch C reviewed literature-review degrees-of-freedom, publication-bias,
  model-uncertainty, multiverse, and branch-and-bound citations.
- Batch D reviewed preregistration, pre-analysis-plan, and strategic-reporting
  citations.
- Batch E reviewed experimental, observational, omitted-variable-bias
  sensitivity, and design-phase citations.
- Batch F reviewed post-selection, high-dimensional, restricted-isometry, and
  restricted-eigenvalue citations.
