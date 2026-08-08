# Model Definition and Evaluation

**[Notebook](model_definition_evaluation)**


- **Model Selection**: Baseline models included logistic regression and random forest, and a LightGBM classifier was additionally evaluated as a boosting-based model.

- **Feature Engineering**: We used species-level metagenomic profiles derived from HMP2/IBDMDB as predictors of diagnosis class (`UC`, `CD`, `nonIBD`). To avoid subject leakage, model evaluation used a subject-level split based on `sample_id`, ensuring that samples from the same subject did not appear in both training and test sets. 

- **Hyperparameter Tuning**: Hyperparameter tuning used `RandomizedSearchCV` with 3-fold group cross-validation and a small search budget (`n_iter=3`) to keep runtime manageable.

- **Implementation**: Missing values in the feature matrix were handled within the model pipeline, and categorical clinical metadata were excluded from the MGX-only classification model to prevent label leakage.

- **Evaluation Metrics**: Model performance was assessed using accuracy, macro F1, weighted F1, confusion matrices, and multiclass ROC/precision-recall curves. Macro F1 was emphasized because it treats all classes equally and is informative under class imbalance.

- **Comparative Analysis**: Among the tested models, LightGBM achieved the best performance and was therefore selected as the final model for the MGX-based diagnosis prediction task.