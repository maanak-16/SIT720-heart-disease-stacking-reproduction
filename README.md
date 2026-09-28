# SIT720 11.1 HD Task — Option 3

**An efficient stacking-based ensemble technique for early heart attack prediction**

## Package contents
- `SIT720_heart_disease_stacking_study.ipynb` — notebook with all outputs (Part 1 reproduction and Part 2 LASSE).
- `SIT720_report.pdf` — technical research report.
- `heart.csv` — dataset used for the experiments.
- `requirements.txt` — pinned Python package versions.
- `results/` — result tables and statistical outputs.
- `figures/` — ROC curves and confusion matrices.

## Reproduction
1. Use Python **3.13.5**.
2. Create and activate a clean virtual environment.
3. Install the pinned packages:

```bash
pip install -r requirements.txt
```

4. Place `heart.csv` in the same folder as the notebook.
5. Open `SIT720_heart_disease_stacking_study.ipynb` and run it from top to bottom.
6. Runtime depends on the computer because the repeated tuning and model comparisons require more computation than the single holdout experiment.

The reproducibility environment is Python 3.13.5 with the package versions pinned in `requirements.txt`.

## Dataset source
The selected paper identifies the Public Health Dataset at:
https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset?datasetId=216167&sortBy=voteCount

## Presentation and code archive
Video presentation: https://deakin.au.panopto.com/Panopto/Pages/Viewer.aspx?id=de5213a8-9c89-4fd4-bd4a-b4d300770601

Code repository: https://github.com/maanak-16/SIT720-heart-disease-stacking-reproduction

## Main findings
The supplied file contains 1,025 rows but only 302 unique rows. Under the seed-42 paper-style split, 202 test observations have identical predictor vectors in training. Paper-style stacking reaches 1.0000 accuracy on that split.

Across the matched ten-seed protocol comparison, paper-style stacking averages 0.9971 ± 0.0062 accuracy while leakage-aware stacking averages 0.8492 ± 0.0603, a mean gap of 0.1479. Paper-style accuracy is higher in all 10 nominal seed cases. The unpaired Mann–Whitney U comparison gives **p < 0.001**; the Wilcoxon calculation is retained only as a sensitivity calculation because the two protocols use different row-level datasets.

LASSE does not show a statistically significant accuracy improvement over leakage-aware stacking. The report therefore presents the main contribution as improved experimental validity and reproducibility rather than unsupported predictive superiority.
