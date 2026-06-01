# Baseline Model

**[Notebook](baseline_model.ipynb)**

## Baseline Model Results

### Model Selection
- **Baseline Model Type:** Logistic Regression
- **Rationale:** Standard model for classification

### Model Performance
- **Evaluation Metric:** Accuracy, F1-score, Precision, Recall (weighted and macro averages)
- **Performance Score:** Accuracy: 63%, F1-score (weighted): 0.64, F1-score (macro): 0.62
- **Cross-Validation Score:** Not done yet 
- WIP: 
    Confusion matrix
    Class 0 (UC): precision=0.49, recall=0.71, F1=0.58, support=301
    Class 1 (CD): precision=0.78, recall=0.58, F1=0.67, support=537
    Overall accuracy: 0.63


### Evaluation Methodology
- **Data Split:** 80% train / 20% test with stratified sampling (to maintain 64% CD / 36% UC ratio in both sets) 
- **Evaluation Metrics:** Accuracy, Precision, Recall, F1-score (both macro and weighted averages), Confusion Matrix

Justification of these metrics for this problem: 
1. Class imbalance exists (64% CD vs 36% UC) 
2. F1-score: balances precision and recall, which is preferred for imbalanced classification
3. Recall is clinically important — missing a CD diagnosis (false negative) has different consequences than misclassifying UC as CD (false positive)
4. Confusion matrix shows which errors the model makes, which matters more than a single number

### Metric Practical Relevance
For IBD Subtype Classification (UC vs CD): 
- Accuracy (63%) means overall proportion of correct predictions. 
    Impact: Limited value — in this case, a model that always predicts CD would achieve 64% accuracy without learning anything. Accuracy alone is misleading for imbalanced data 
- Precision for CD (0.78): When the model predicts CD, 78% of those predictions are correct	
    Impact: High precision means fewer false positives — fewer UC patients incorrectly treated for CD (avoids unnecessary Crohn's-specific therapies) 
- Recall for CD (0.58):	The model correctly identifies 58% of actual CD cases
    Impact: Low recall is concerning — 42% of CD patients would be missed (false negatives), potentially delaying appropriate CD treatment 
- Recall for UC (0.71):	The model correctly identifies 71% of actual UC cases. 
    Impact: Better than CD recall, but still 29% of UC patients misclassified as CD 
- F1-score (weighted: 0.64): Balanced measure accounting for both precision and recall. 
    Impact: More informative than accuracy for imbalanced datasets — reflects the trade-off between false positives and false negatives 
- Confusion Matrix shows exactly which patients are misclassified. 
    Impact: Critical for clinical decision-making — reveals the model confuses 224 CD as UC and 86 UC as CD, which is substantial clinical error 


Real-World Implications: 
- CD predicted as UC (false negative for CD): Patient may miss essential Crohn's-specific treatments (e.g., anti-TNF, biologics); risk of complications like strictures/fistulas worsens 
- UC predicted as CD (false positive for CD): Patient may receive unnecessary Crohn's medications; may not get appropriate UC-specific therapy (e.g., colectomy considerations) 
- Model accuracy of 63%: Not clinically acceptable for standalone diagnosis — human gastroenterologists achieve >90% diagnostic accuracy with clinical evaluation + imaging 
- F1-score of 0.64:	Moderate performance — suggests the model has some signal but needs improvement (better features, more data, or omics integration) 


## Next Steps
This baseline model serves as a reference point for evaluating more sophisticated models in the [Model Definition and Evaluation](../3_Model/README.md) phase.
