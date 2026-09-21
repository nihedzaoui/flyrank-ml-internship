# Capstone Report — Content Refresh Prioritization

**Author:** Nihed Zaoui  
**Lane:** Machine Learning  
**Date:** 2026-09-21

## 0. Abstract

This study asks whether observable content-performance signals can help rank pages for refresh review more effectively than a transparent rule-based queue. The reproducible public release contains 30,000 pseudonymized content items and 44 columns, while the internship workflow is designed to scale to a larger hosted release without publishing private production data. Decline is defined from the observed trend_direction field, which is excluded from the model together with trend_pct, identifiers, and other target-derived variables. A Random Forest evaluated with a client-holdout split achieved Precision@50 of 0.740 versus 0.240 for the rule baseline, with ROC-AUC 0.750 versus 0.627. The resulting score is decision support for human review, not evidence that refreshing a page will cause future search performance to improve.

## 1. Problem framing

The practical decision is which existing pages an editor should inspect first for a possible refresh. The unit of analysis is one pseudonymized content item; the output is a ranked review queue followed by human inspection.

## 2. Data safety

The public repository contains a 30,000-row anonymized starter release with 44 columns. It contains pseudonymized identifiers, numeric/categorical content metadata, search-performance measurements, freshness fields, and derived trend fields. Client and content IDs are used only for grouping/validation and are never model features.

Target: is_declining_label = (trend_direction == down).

The model excludes content_id, client_id, trend_direction, trend_pct, and is_declining_label. The larger hosted internship release is not copied into this public repository; the paper reports the reproducible public release rather than implying unpublished production rows are available.

## 3. Baseline

The transparent refresh-opportunity rule reports Precision@50 = 0.240. The model comparison uses the same ranking metric and client-holdout evaluation design.

## 4. Model / analysis

The model is a Random Forest classifier whose positive-class probability is used as a ranking score. A GroupShuffleSplit holds out approximately 20% of clients. In the notebook run, 25 clients were used for training and 7 for testing, with no client overlap.

The model uses 40 leakage-safe input columns, including search demand, engagement, freshness, content-length, position, and content-type signals. Categorical variables are imputed and one-hot encoded; numeric variables use median imputation. Leakage checks explicitly exclude target-derived trend variables.

## 5. Evaluation

| Method | ROC-AUC | Average Precision | Precision@50 | Recall | F1 |
|---|---:|---:|---:|---:|---:|
| Rule baseline | 0.627 | 0.468 | 0.240 | — | — |
| Random Forest | 0.750 | 0.618 | **0.740** | 0.744 | 0.640 |

The task base rate is 54.2%, so Precision@50 should be interpreted against both prevalence and the explicit baseline.

The strongest reported feature-importance signals were days_with_impressions, log-scaled 90-day impressions, average position, and content age. These are associations learned by the model, not causal explanations.

## 6. Limitations

1. The target is a proxy derived from observed trend information, not a direct measure of editorial quality.
2. The data is observational; the analysis does not establish that refreshing a page causes future performance to improve.
3. The public artifact is based on the reproducible 30,000-row anonymized release, not the private full production warehouse.
4. Client-grouped validation is stricter than random row splitting when client-specific patterns exist.
5. Model probabilities are ranking signals, not calibrated business-outcome probabilities without additional validation.
6. Human review remains necessary; the system does not automatically publish, refresh, redirect, or rewrite content.

The appropriate interpretation is: the model ranks pages that look worth reviewing first, given the observed signals and this validation design.

## 7. Ranked recommendations

1. Review high-confidence candidates first and verify the page and editorial context.
2. Check the visible opportunity using impressions, CTR, engagement, position, and freshness as evidence rather than automatic instructions.
3. Separate CTR and engagement diagnoses before selecting an intervention.
4. Keep a human approval gate; the model output is a review queue, not an automatic publishing decision.
5. Monitor prospectively; if refreshes occur, collect pre/post outcomes and use an appropriate time-aware or experimental design before making causal claims.

## 8. Reproducibility

Inspect the ML-08 model notebook, ML-09 validation audit, ML-10 action playbook, capstone notebook, and outputs/model_report.md in the repository. From a fresh clone, install requirements with `pip install -r requirements.txt` and run `python scripts/run_all.py`. The reference configuration uses random seed 42. Generated datasets remain outside the public repository according to the project data-use rules.

## 9. Acknowledgments & data credit

Built on the FlyRank ML Internship dataset: https://flyrank.ai

This artifact uses public-safe aggregate reporting and does not publish client names, domains, URLs, page titles, keywords, or raw search queries.
