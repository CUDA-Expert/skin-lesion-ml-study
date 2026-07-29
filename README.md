<p align="center">
  <img src="./assets/cover.svg" width="100%" alt="Skin Lesion Malignancy Study" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Domain-Medical%20Imaging-EC4899?style=flat-square" alt="Medical imaging" />
  <img src="https://img.shields.io/badge/Challenge-Extreme%20Imbalance-F97316?style=flat-square" alt="Extreme class imbalance" />
  <img src="https://img.shields.io/badge/Public%20Edition-Research%20Case%20Study-334155?style=flat-square" alt="Research case study" />
</p>

An academic study of skin lesion malignancy classification in the ISIC 2024
setting, where a clinically important positive class represents roughly one
tenth of one percent of the available cases.

> Developed collaboratively as a university team project. This repository
> presents the research design and evidence boundary; notebooks, reports, and
> data dependent artifacts remain in a private archive.

## The central problem

<table>
  <tr>
    <td align="center"><strong>401,059</strong><br />total cases</td>
    <td align="center"><strong>393</strong><br />malignant cases</td>
    <td align="center"><strong>≈ 0.1%</strong><br />positive prevalence</td>
    <td align="center"><strong>5</strong><br />preserved notebooks</td>
  </tr>
</table>

With this level of imbalance, a model can report excellent accuracy while
missing nearly every malignant case. The study therefore centers sensitivity,
specificity, precision, recall, calibration, and threshold behavior instead of
treating raw accuracy as sufficient evidence.

## Study design

```mermaid
flowchart LR
    A[ISIC images and metadata] --> B[Quality review and preprocessing]
    B --> C[Targeted minority augmentation]
    C --> D[ResNet50 representation learning]
    D --> E[Logistic regression]
    D --> F[Support vector machine]
    D --> G[CNN track]
    E --> H[Threshold and error analysis]
    F --> H
    G --> H
```

## Method map

| Stage | Purpose |
| --- | --- |
| Image preprocessing | Standardize inputs and inspect quality variation |
| Targeted augmentation | Increase minority exposure without claiming new patients |
| ResNet50 representations | Produce 2,048 dimensional features from ImageNet weights |
| Logistic regression and SVM | Compare classical decision boundaries |
| Imbalance handling | Reduce majority class dominance during learning |
| Threshold analysis | Examine sensitivity and false positive tradeoffs |

## Evidence status

The private archive preserves the CNN, logistic regression, SVM, and
preprocessing notebooks together with the academic report and model notes.

| Check | Result |
| --- | --- |
| Selected notebook structure | 5 valid notebook files |
| Archive integrity | Preserved files match the original archive by SHA256 |
| Full training rerun | Not completed during portfolio preparation |
| External clinical validation | Not performed |

Some notebooks still depend on local paths and on data that is not distributed
through GitHub. The project therefore remains a research archive until the
experiment is rebuilt around a documented, patient level protocol.

## What the study does not claim

1. It is not a clinically validated diagnostic system.
2. It does not establish performance on an external hospital population.
3. Augmented images do not replace independent malignant examples.
4. Notebook outputs do not replace a frozen evaluation protocol.

## Public and private boundary

This public repository contains the research question, methodology, evidence
status, limitations, and next steps. The notebooks and report remain private
while reproducibility, team approval, and dataset handling are reviewed. The
large ISIC image collection is not stored in GitHub.

## Roadmap

1. Rebuild the experiment around a documented patient level split.
2. Compare weighting, sampling, and focal loss under one protocol.
3. Report confidence intervals, calibration, and threshold curves.
4. Add subgroup and failure mode analysis.
5. Package preprocessing and evaluation as reproducible stages.

## Responsible use

This project is educational research. It must not be used for diagnosis or
clinical decision making. Any future release should point to the official ISIC
data source instead of redistributing medical images.
