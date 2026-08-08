# Baseline Model

**[Notebook](baseline_model.ipynb)**

## Baseline Model Results

### Model Selection
- **Baseline Model Type:** Logistic regression (LR) and random forest (RF). 
- **Rationale:** LR and RF were the standard baseline classifier. 

### Model Performance
- **Evaluation Metric:** Accuracy, macro F1-score, weighted F1-score, precision, recall, and confusion matrix.
- **Performance Score:** 
    * Logistic regression: test accuracy 0.943, macro F1 0.941
    * Random forest: test accuracy 0.978, macro F1 0.977
- **Cross-Validation Score:** 3-fold group cross-validation with RandomizedSearchCV.


### Evaluation Methodology
- **Data Split:** 80% train / 20% test with **subject-level splitting** using `sample_id` to avoid train-test leakage.
- **Evaluation Metrics:** Accuracy, precision, recall, macro F1, weighted F1, confusion matrix, ROC curves, and precision-recall curves.

Justification of these metrics for this problem: 
1. Class imbalance exists (CD is the largest class, followed by UC and nonIBD.)
2. Macro F1-score: it treats all classes equally and balances precision and recall, which is preferred for imbalanced classification. 
3. Precision and recall: help describe how well the model distinguishes each diagnosis class, and they are clinically important — missing a CD diagnosis (false negative) has different consequences than misclassifying UC as CD (false positive)
4. Confusion matrix shows which diagnoses are most often confused, which is important for medical interpretation.
5. ROC and PR curves provide an additional view of classifier quality across thresholds.

### Metric Practical Relevance
For diagnosis classification (UC / CD / nonIBD)

| Metric | Impact | 
|---|---|
| Accuracy (0.947 for LightGBM): Overall proportion of correct predictions. | High accuracy indicates strong overall classification performance, but it should still be interpreted alongside class-wise metrics.
| Macro F1 (0.946 for LightGBM): Average F1 across all classes, treating each class equally. | Very useful when class sizes differ, because it shows that the model performs well on UC, CD, and nonIBD rather than being dominated by the largest class.
| Precision for CD (0.96): When the model predicts CD, it is correct 96% of the time. | Few false positives for CD, which is important when subtype-specific interpretation matters.
| Recall for CD (0.94): The model identifies 94% of true CD samples. | Low missed-case rate for CD.
| Precision and recall for UC and nonIBD: Both are above 0.90. | The model generalizes well across all three classes.
| Confusion matrix: Shows only a small number of misclassifications among classes. | Important for understanding whether the model confuses biologically similar groups, such as UC and CD. | 



Real-World Implications: 
* Strong microbiome signal: The MGX species-level data are highly informative for separating UC, CD, and nonIBD, suggesting that disease-associated dysbiosis is strong in this cohort.

* Clinical relevance: High performance indicates that stool metagenomic profiles capture biologically meaningful subtype differences.

* Why not use the earlier metadata-response endpoint: The original therapy-response framing was too ambiguous because the metadata contained diagnosis-related variables but did not provide a clean, unambiguous response label. Using those variables directly would have introduced label leakage and overly optimistic performance.

* Practical interpretation: The MGX model is a much more valid prediction task than the metadata-based response model, because it predicts diagnosis from microbial features rather than reconstructing a label already embedded in the metadata.


## Next Steps
This baseline model serves as a reference point for evaluating more sophisticated models in the [Model Definition and Evaluation](../3_Model/README.md) phase.
