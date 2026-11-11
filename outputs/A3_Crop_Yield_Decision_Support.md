# Crop-yield decision support (one-page summary)

**Group members:**
1. Maxwell Mbondo - 24/06667
2. Mark Kitema - 24/06543
3. Hamdi Mohamed - 24/08115
4. Feisal Noor - 24/07112


**Question and data.** Explore yield patterns and assess basic prediction on the synthetic `A3_Crop_Yield` worksheet. Target: yield (tonnes/ha); predictors: area, rainfall, temperature, fertilizer, county, crop, soil and irrigation. `Farm_ID` is excluded. After dropping the repeated exact farm record, 200 records remain. Missing numeric values are retained and imputed by training-fitted medians; missing soil is labeled Unknown. One zero farm area is set missing. Rainfall values above 2,000 mm are flagged for verification and kept.

**Three findings.** (1) Mean yield is 4.21 and median yield 3.24 tonnes/ha; the bootstrap 95% interval for the sample mean is 3.72–4.72. (2) Potatoes has the highest observed crop-group mean (12.00, n=32), while Beans is lowest (1.58, n=55); groups differ in crop conditions and sample sizes. (3) Spearman correlations are 0.30 for rainfall and 0.16 for fertilizer with yield. These are associations, not causal responses. Irrigation-group median difference (Yes minus No) is 0.38 tonnes/ha; the Mann–Whitney test p-value is 0.036, which does not establish an irrigation effect.

**Model comparison.** On the same held-out split, the best test-MAE model was **Random forest**: MAE 0.61, RMSE 0.83 tonnes/ha, R-squared 0.95. See `outputs/A3_Crop_Yield_model_comparison.csv` and the labelled observed-versus-predicted plot. The sample is small; county-level holdout validation is a stronger next test.

**Cautious recommendations.** Use these summaries only to frame questions for local, representative data collection; do not prescribe fertilizer, irrigation or crop changes from these associations. Verify the flagged rainfall and zero-area record against source records and collect contextual information (season, seed variety, management, soil measurements and measurement methods) before any operational use.

## What this analysis cannot establish
These synthetic records cannot establish real Kenyan farm outcomes, representative county rankings, causal effects of inputs or reliable future performance. Missing values, potential sampling bias, repeated patterns, unusual rainfall, omitted agronomic factors and a small sample create uncertainty. Feature importance or a correlation is not evidence that changing an input will raise yield.

## Ethics and limitations reflection
No real farmer is represented in this workbook, but a real deployment could expose sensitive information about land, income, location or agricultural practices. Farmers should understand the purpose and uses of data and participate voluntarily where appropriate. Collect only variables needed for a clearly stated purpose, document ownership and permitted reuse, restrict access by role, encrypt data in transit and at rest and define retention and deletion procedures. Do not assume that a county or crop group is fairly represented merely because it appears in the sample; small farms and under-sampled communities can be hidden by aggregate averages. Explain model limitations in language users can understand and provide a way to challenge inaccurate records or decisions. If personal data are involved, assess obligations under the Kenya Data Protection Act and applicable regulations with qualified guidance. Models trained on observational records can reproduce historical inequities and should not determine access to inputs, credit or support without human review, representative validation and accountability. In this exercise, the simulated provenance, missing contextual variables and random split mean model scores are illustrative only. Any real recommendation should be based on verified local evidence, uncertainty intervals, agronomic expertise and farmer priorities rather than a single score or feature-importance ranking.
