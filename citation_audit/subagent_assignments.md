# Citation Audit Subagent Assignments

Each reviewer should inspect the citation rows assigned below in
`citation_audit/citation_contexts.tsv`, read the corresponding local source
artifact under `sources/`, and judge whether the cited paper reasonably supports
the local manuscript claim.

For each assigned citation ID, return:

- `citation_id`
- `key`
- `status`: `supported`, `weak`, `mismatch`, or `metadata`
- `rationale`: one concise sentence tied to the source
- `suggested_action`: `none`, `rewrite`, `move citation`, `remove citation`,
  `add qualifier`, or `fix metadata/source`

Review standards:

- Judge the citation in context, not just whether the paper is generally on topic.
- Mark `supported` when the source plainly supports the local claim.
- Mark `weak` when the source is relevant but the prose is broader than the paper.
- Mark `mismatch` when the source is misplaced or does not support the claim.
- Mark `metadata` for bibliographic/source artifact problems.
- Do not edit manuscript files directly; report findings for integration.

## Batch A: Introduction, Methodological Foundations

High-priority introduction citation contexts:

- `CIT-0001` `simmonsFalsePositivePsychologyUndisclosed2011`
- `CIT-0002` `johnMeasuringPrevalenceQuestionable2012`
- `CIT-0003` `kerr1998harking`
- `CIT-0004` `gelmanLoken2013`
- `CIT-0005` `wicherts2016degrees`

## Batch B: Introduction, Field-Level Diagnostics

High-priority introduction citation contexts:

- `CIT-0006` `franco2014publication`
- `CIT-0007` `head2015extent`
- `CIT-0008` `brodeur2016star`
- `CIT-0009` `brodeur2020methods`
- `CIT-0010` `vivalt2019specification`
- `CIT-0011` `jerke2025publication`
- `CIT-0012` `andrews2019identification`
- `CIT-0013` `elliott2022detecting`

## Batch C: Literature Review, Degrees of Freedom and Specification Surfaces

- `CIT-0014` `simmonsFalsePositivePsychologyUndisclosed2011`
- `CIT-0015` `johnMeasuringPrevalenceQuestionable2012`
- `CIT-0016` `wicherts2016degrees`
- `CIT-0017` `kerr1998harking`
- `CIT-0018` `gelmanLoken2013`
- `CIT-0019` `gelman2014crisis`
- `CIT-0020` `rosenthal1979file`
- `CIT-0021` `franco2014publication`
- `CIT-0022` `brodeur2016star`
- `CIT-0023` `head2015extent`
- `CIT-0024` `brunsIoannidis2016pcurve`
- `CIT-0025` `brodeur2020methods`
- `CIT-0026` `vivalt2019specification`
- `CIT-0027` `jerke2025publication`
- `CIT-0028` `andrews2019identification`
- `CIT-0029` `elliott2022detecting`
- `CIT-0030` `leamer1983con`
- `CIT-0031` `salaimartin1997twoMillion`
- `CIT-0032` `young2009modelUncertainty`
- `CIT-0033` `youngModelUncertaintyRobustness2017`
- `CIT-0034` `knaeble2024branch`
- `CIT-0035` `steegenIncreasingTransparencyMultiverse2016`
- `CIT-0036` `simonsohnSpecificationCurveDescriptive2019`
- `CIT-0037` `silberzahn2018many`
- `CIT-0038` `breznau2022hidden`
- `CIT-0039` `rohrer2026multiverse`

## Batch D: Literature Review, Preregistration and Strategic Reporting

- `CIT-0040` `nosek2018preregistration`
- `CIT-0041` `olken2015promises`
- `CIT-0042` `banerjee2020praise`
- `CIT-0043` `kasy2021forking`
- `CIT-0044` `brodeurPreregistrationPreanalysisPlans2024`
- `CIT-0045` `andrews2021model`
- `CIT-0046` `libgober2022false`
- `CIT-0047` `mccloskey2022incentive`
- `CIT-0048` `spiess2018optimal`
- `CIT-0049` `kasy2022optimal`

## Batch E: Literature Review, Experimental and Observational Causal Claims

- `CIT-0050` `lin2013agnostic`
- `CIT-0051` `robinsRitov1997coda`
- `CIT-0052` `aronowRobinsSaarinenSavjeSekhon2021`
- `CIT-0053` `kingDetectingModelDependence2007`
- `CIT-0054` `lenz2021achieving`
- `CIT-0055` `sturman2022uncontrolled`
- `CIT-0056` `yu2024misstatements`
- `CIT-0057` `cinelliForneyPearl2022crash`
- `CIT-0058` `oster2019unobservable`
- `CIT-0059` `cinelliHazlett2020sensitivity`
- `CIT-0060` `chernozhukov2022long`
- `CIT-0061` `cinelliHazlett2025iv`
- `CIT-0062` `tsao2025minimum`
- `CIT-0063` `choi2025designPhase`

## Batch F: Post-Selection, High-Dimensional, and RIP Geometry

- `CIT-0064` `cox1975dataSplitting`
- `CIT-0065` `berk2013valid`
- `CIT-0066` `fithian2014optimal`
- `CIT-0067` `lee2016exact`
- `CIT-0068` `kuchibhotla2018assumptionLean`
- `CIT-0069` `kuchibhotlaKolassaKuffner2022postSelection`
- `CIT-0070` `tianTaylor2018selective`
- `CIT-0071` `berk2013valid`
- `CIT-0072` `el2013robust`
- `CIT-0073` `sur2019likelihood`
- `CIT-0074` `hastie2022surprises`
- `CIT-0075` `candesTao2005decoding`
- `CIT-0076` `baraniuk2008simple`
- `CIT-0077` `bickelRitovTsybakov2009`
- `CIT-0078` `vandegeerBuhlmann2009conditions`
- `CIT-0079` `raskuttiWainwrightYu2010restricted`
- `CIT-0080` `candesTao2005decoding`
- `CIT-0081` `baraniuk2008simple`
- `CIT-0082` `bickelRitovTsybakov2009`
- `CIT-0083` `vandegeerBuhlmann2009conditions`
- `CIT-0084` `raskuttiWainwrightYu2010restricted`
