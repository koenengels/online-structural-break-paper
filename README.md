# Causal Feature Engineering and Learned Residual Evidence for Online Structural Break Detection

**Koen Engels** · Technical competition report · 28 October 2026

Write-up for the ADIA Lab Structural Break Real-Time Challenge on CrunchDAO (selected submission #46, public leaderboard 0.6191).

- [PDF](Engels_online_structural_break_detection.pdf)
- [Web version](https://koenengels.github.io/online-structural-break-paper/)

## Abstract

The Abu Dhabi Investment Authority (ADIA) supports the independent research institute ADIA Lab. I study causal structural-break detection in its Real Time Challenge with CrunchDAO. The task requires a score after every online observation and evaluates cross-sectional ranking using time-stratified area under the receiver operating characteristic curve (TS-AUC).

My selected submission combines engineered statistical features, autoregressive residual representations and a Light Gradient Boosting Machine (LightGBM) student trained on nested cross-fitted soft labels. It achieved a recorded public leaderboard score of 0.6191.

Subsequent offline research examines learned normal-process models, neural and pretrained forecasting representations, nested width selection, temporal blending and sequential residual evidence. On matched search folds, a combination using a selected-width gated recurrent unit (GRU) null model scores 0.622489, and adding sequential mean, energy and lag-product evidence raises the mean to 0.623224. The incremental gain is positive in nine of fifteen fold–seed cells, but fails all five two-half bootstrap gates for every tree seed against the preceding combination. Temporal analysis locates most of the additional gain before online step 100, with a regression between steps 100 and 249. A subsequent 8,000-series likelihood search for generalized autoregressive score models with Student-t innovations (GAS-t) raises its matched blend from 0.619810 to 0.620676, but fails all 105 declared gates and remains below the GRU combinations.

I document scorer and leakage corrections, distinguish search evidence from fixed-holdout confirmation, and report unsuccessful methods alongside promising candidates. As of 28 October 2026, submission 46 remains the selected recorded public result; the competition run window is closed, and neither sequential residual evidence nor the GAS-t blend has received a new public score or a registered holdout confirmation. The results support complementary residual representations as a research direction, while leaving replacement of the selected submission unconfirmed.

**Keywords:** online structural break detection; time-stratified AUC; feature engineering; nested cross-fitting; soft labels; learned null models; stacking; sequential evidence; cluster bootstrap.
