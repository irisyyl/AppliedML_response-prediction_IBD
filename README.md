# Applied Machine Learning: Prediction of IBD Subtype Using Multi-omics Data

## Repository Link
https://github.com/irisyyl/AppliedML_response-prediction_IBD

## Description
This project uses HMP2/IBDMDB metagenomic taxonomic profiles and clinical metadata to predict IBD subtype (`UC`, `CD`, `nonIBD`) and explore microbiome-associated disease structure. We began by examining clinical metadata and disease subtype distributions, then built models using species-level microbiome features to assess how well omics data can discriminate between disease classes.

##### Approach 
We first explored the clinical metadata across IBD subtypes to understand class balance and potential sources of signal. Because the clinical table did not provide a clean therapeutic-response endpoint, we pivoted the project to a three-class classification task: predicting UC, CD, and nonIBD from MGX species-level profiles.

Next, we built a microbiome feature matrix from the taxonomic profiles, merged it with the metadata using the correct sample identifier, and evaluated multiple models. We used subject-level splitting to avoid leakage and compared logistic regression, random forest, and LightGBM. The final model was selected based on cross-validation and held-out test performance.

### Task Type
Classification: predict IBD subtype (`UC`, `CD`, `nonIBD`) using metagenomic features.

### Results Summary

#### Best Model Performance
- **Best Model:** LightGBM (boosting-based method)
- **Evaluation Metric:** Accuracy, macro F1-score, weighted F1-score, confusion matrix, ROC curves, precision-recall curves
- **Final Performance:** 
    - Accuracy: 0.947
    - Macro F1: 0.946
    - Weighted F1: 0.947

#### Model Comparison
- **Baseline Performance:** Logistic regression, random forest
- **Improvement Over Baseline:** LightGBM outperformed logistic regression and random forest on the held-out test set, with the strongest macro F1 and accuracy.
- **Best Alternative Model:** Random forest 

#### Key Insights
- **Most Important Features:**  The most informative taxa included multiple *Bacteroides* species, *Faecalibacterium prausnitzii*, *Akkermansia muciniphila*, *Roseburia spp.*, and *Ruminococcus/Lachnospiraceae* members, consistent with prior IBD literature linking loss of beneficial anaerobes and expansion of inflammation-associated taxa to disease state. These features likely capture differences in mucosal inflammation, carbohydrate fermentation, and bile-acid-associated ecology across diagnoses.
- **Model Strengths:** The microbiome profiles provided strong predictive signal for separating `UC`, `CD`, and `nonIBD`. The model remained strong under subject-level splitting, suggesting the result is not driven by train-test contamination.
- **Model Limitations:** The project focuses on subtype classification rather than therapeutic response because the available metadata did not contain a clean response endpoint. Also, the model depends on microbiome profiles from the HMP2 cohort and may not generalize directly without external validation.
- **Business Impact:** The results show that stool metagenomic profiles can capture subtype-specific microbial structure and may support downstream biomarker discovery or disease stratification.

## Documentation

1. **[Literature Review](0_LiteratureReview/README.md)**
2. **[Dataset Characteristics](1_DatasetCharacteristics/exploratory_data_analysis.ipynb)**
3. **[Baseline Model](2_BaselineModel/baseline_model.ipynb)**
4. **[Model Definition and Evaluation](3_Model/model_definition_evaluation)**
5. **[Presentation](4_Presentation/README.md)**

## Cover Image

![Project Cover Image](CoverImage/cover_image.png)
