\# Probabilistic Round-Win Prediction in Professional Counter-Strike 2



\*\*Module:\*\* AB LDSCI7237 Artelligence Dissertation Project

\*\*Submission Phase:\*\* Assessment Element 2 (AE2)

\*\*Author:\*\* Farabdeep Arora



\## Abstract

This dissertation project presents the development of a calibrated and leak-free predictive model for estimating round-win probabilities in professional \*Counter-Strike 2 (CS2)\*.



The study addresses a critical integrity gap in current esports forecasting: the prevalence of 'look-ahead bias' in existing public models. By strictly utilising \*\*Start-of-Round (Freeze-Time)\*\* features and introducing a novel \*\*Frozen Pre-Event Elo\*\* rating system, this research delivers a forecasting tool that is both operationally robust and empirically trustworthy.



The final model, constructed using \*\*Gradient-Boosted Decision Trees (LightGBM)\*\* and corrected via \*\*Isotonic Regression\*\*, demonstrates that high-integrity modelling can significantly outperform naïve baselines without compromising on data leakage protocols.



\## Core Research Contributions



\### 1. Integrity-First Methodology (The Frozen Prior)

To prevent temporal leakage, team strength ratings (Elo) are calculated exclusively from match history \*prior\* to the target event. These ratings are frozen throughout the tournament prediction cycle, ensuring the model never benefits from future information (in-event updates).



\### 2. Calibrated Probabilistic Forecasting

Unlike standard classification models that prioritise accuracy (discrimination), this project prioritises \*\*trustworthiness\*\* (calibration). Through post-hoc calibration, the model achieved an \*\*Expected Calibration Error (ECE) of ≤ 0.03\*\*, ensuring that predicted probabilities align closely with empirical win frequencies.



\### 3. Robust Validation Framework

Evaluation was conducted using a strict \*\*Time-Aware, Event-Grouped Cross-Validation\*\* strategy. The model was tested solely on unseen future tournaments to simulate real-world deployment conditions and assess robustness against concept drift (meta changes).



\## Performance Results



The model was evaluated using \*\*Proper Scoring Rules\*\* to penalise overconfidence and reward calibration quality.



| Model Hierarchy | Log Loss (Primary Metric) | Brier Score | Relative Improvement |

| :--- | :--- | :--- | :--- |

| \*\*Baseline A\*\* (Context Prior) | 0.702 | 0.245 | - |

| \*\*Baseline B\*\* (Freeze-Time Economy) | 0.638 | 0.221 | +9.1% |

| \*\*Main Model\*\* (GBT + Frozen Elo) | \*\*0.587\*\* | \*\*0.201\*\* | \*\*+17.2%\*\* |

