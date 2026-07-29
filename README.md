# Skin Lesion Malignancy Study

An academic machine learning study of malignancy classification under extreme
class imbalance using the ISIC 2024 challenge setting.

The work was completed as a university team project. Mohammed Yousef Rasheed
focused on the CNN and image preprocessing track.

## Research Question

How should a machine learning pipeline be designed when the positive class is
clinically important but represents roughly one tenth of one percent of the
available cases?

This project studies the consequences of that imbalance across preprocessing,
representation learning, classical classification, and threshold selection.
Raw accuracy is not treated as sufficient evidence.

## Study Scope

The project explored:

* image cleaning and preprocessing
* targeted augmentation for minority examples
* ImageNet pretrained ResNet50 representations
* logistic regression and support vector machine baselines
* imbalance handling
* decision threshold selection

## Method Map

| Stage | Purpose |
| --- | --- |
| image preprocessing | standardize visual inputs and inspect quality variation |
| targeted augmentation | increase minority class exposure without claiming new patients |
| ResNet50 representations | extract 2,048 dimensional image features |
| logistic regression and SVM | compare interpretable classical decision boundaries |
| imbalance handling | reduce majority class dominance during learning |
| threshold analysis | study sensitivity and false positive tradeoffs |

## Why the Imbalance Matters

A classifier can achieve superficially high accuracy while missing nearly every
malignant case. The meaningful questions are therefore about sensitivity,
specificity, precision, recall, calibration, threshold behavior, and validation
under a fixed patient level split.

## Private Research Archive

The private development repository preserves:

* CNN notebook
* logistic regression notebooks
* SVM and preprocessing notebooks
* academic report
* CNN model notes

The large image dataset and derived image folders are not stored in GitHub.

## Reproducibility Status

All five selected notebooks in the private archive parse as valid notebook files,
and every preserved file matches the original archive by SHA256.

The training pipeline was not rerun during portfolio preparation. Some notebooks
contain local machine paths and depend on data that is not stored in GitHub, so
the source remains private until a team approved reproducibility pass is
completed.

## Source Availability

This public repository documents the research question, methodology, contribution,
evidence, and limitations. The notebooks and academic report remain in the
private team archive.

## What This Repository Does Not Claim

* it is not a clinically validated diagnostic model
* it does not establish performance on an external hospital population
* augmentation does not replace independent malignant examples
* notebook outputs are not a substitute for a frozen evaluation protocol

## Next Technical Milestones

* rebuild the experiment around a documented patient level split
* isolate preprocessing, feature extraction, and evaluation into reproducible stages
* report confidence intervals and threshold curves
* compare class weighting, sampling, and focal loss under the same protocol
* add calibration and subgroup error analysis

## Responsible Use

This project is educational research. It is not a diagnostic system and must not
be used for clinical decisions. Any public release should link to the official
ISIC data source instead of redistributing images.
