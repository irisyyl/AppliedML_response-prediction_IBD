# Literature Review

Approaches or solutions that have been tried before on similar projects.

**Summary of Each Work**:

- **Source 1**: *Machine Learning Modeling from Omics Data as Prospective Tool for Improvement of Inflammatory Bowel Disease Diagnosis and Clinical Classifications*

  - **[Link](https://pmc.ncbi.nlm.nih.gov/articles/PMC8466305/)**
  - **Objective**: This is a review paper that summarized fundamental principles behind ML modeling and its current application in IBD research with focus on studies that explored genomic and transcriptomic data. 
  - **Methods**:
    - Supervised 
      - Linear algorithms: 
        - Linear regression
        - Logistic regression
        - Ridge regression (L2 regularization)
        - LASSO regression (L1 regularization)
        - Elastic net (L1 and L2 regularization)
      - Non-linear algorithms: 
        - Support vector machines (SVM)
        - K-nearest neighbors
        - Decision trees 
        - Naïve Bayesian algorithms 
        - Neural networks
      
    - Upsupervised 
      - Hierarchical clustering
      - Principal component analysis (PCA)

  - **Outcomes**: The most frequently employed ML methods included penalized regression models, random forest, support vector machines, Bayesian approach and neural networks in recent years in using AI to explore omics data for IBD risk prediction and classification, with AUC ranging from 0.7 to 0.95.  
  - **Relation to the Project**: List out most commonly used classification and/or regression algorithms in IBD research. 

- **Source 2**: *Comparative performances of machine learning methods for classifying Crohn Disease patients using genome-wide genotyping data*

  - **[Link](https://www.nature.com/articles/s41598-019-46649-z)**
  - **Objective**: This article compared ML methods for CD classification using genomic data. 
  - **Methods**: In this paper, they compared three classes of models for case/control classification: logistic regression (LR), dense neural networks (NN) and gradient boosting on decision trees (GBT). 
  - **Outcomes**: Compared to LR, non-linear models such as GBT or NN may provide robust complementary approaches to identify and classify genetic markers.
  - **Relation to the Project**: Compared performance of ML models and pinpointed potential models to identify and classify genetic markers. 

- **Source 3**: *Multi-omics of the gut microbial ecosystem in inflammatory bowel diseases*

  - **[Link](https://www.nature.com/articles/s41586-019-1237-9)**
  - **Objective**: This ariticle used IBDMBD dataset to conduct multi-omics analysis and explored gut microbial ecosystem on IBD patients. 
  - **Methods**: They employed statistical methods and association testing: 
    Statistical methods: 
    - Principal coordinates analysis (PCoA) 
    - Wald test
    - PERMANOVA for quantifications of variance and 
    - Mantel test for quantification of covariation between measurement types
    - Differential microbiome feature abundance
    
  - **Outcomes**: 
  - **Relation to the Project**: Original publication of the working dataset. 

- **Source 4**: *Treat-to-Target in Ulcerative Colitis: How Soon Is Now?*

  - **[Link](https://pmc.ncbi.nlm.nih.gov/articles/PMC12841710/#sec1-jcm-15-00759)**
  - **Objective**: This ariticle explores current evidence and future directions on treat-to-target strategies in UC for clinical research and practice.
  - **Methods**:    
  - **Outcomes**: 
  - **Relation to the Project**: Clinical endpoint for UC. 



ML models to test in this project: Random forest, gradient boosted trees (GBT)