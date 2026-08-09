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
    - Principal coordinates analysis (PCoA): visualize differences in sample composition.
    - Wald test and differential-abundance analysis: identify features associated with disease or dysbiosis.
    - PERMANOVA: quantify the proportion of variation explained by clinical and biological factors
    - Mantel test: quantify covariation between different measurement types
    - Integrative multi-omics analysis: identify relationships between microbial, biochemical, and host factors

    Longitudinal analysis: investigate changes in microbial, biochemical, and host-associated features over time
    
  - **Outcomes**: The study identified coordinated changes across the gut microbial ecosystem during IBD activity. These included increased facultative anaerobes, depletion of obligate anaerobes, disruption of microbial transcription, altered bile-acid and short-chain-fatty-acid profiles, and changes in host serum antibody levels. Disease activity was also associated with increased temporal variability across taxonomic, functional, and biochemical measurements. The study identified complementary signals across multiple omics layers and made the resulting data and infrastructure available through the IBDMDB

  - **Relation to the Project**: Original publication of the working dataset. Although the original study performed broad multi-omics and longitudinal analyses, our project uses a narrower machine-learning task based on species-level MGX profiles and shall be viewed as a predictive extension of the resource rather than a reproduction of the original multi-omics analysis.

- **Source 4**: *Treat-to-Target in Ulcerative Colitis: How Soon Is Now?*

  - **[Link](https://pmc.ncbi.nlm.nih.gov/articles/PMC12841710/#sec1-jcm-15-00759)**
  - **Objective**: This ariticle explores current evidence and future directions on treat-to-target strategies in UC for clinical research and practice.
  - **Methods**: A review and clinical perspective on T2T management in UC. It discusses evidence from randomized controlled trials, real-world studies, clinical guidelines, and ongoing research. The review covers different monitoring approaches, including clinical assessment, fecal calprotectin, C-reactive protein, endoscopy, histology, intestinal ultrasound, and patient-reported outcomes.
  - **Outcomes**: This article describes several categories of treatment targets:
    - **Short-term targets:** Symptomatic response and clinical remission, including improvement in rectal bleeding and stool frequency.
    - **Intermediate targets:** Biochemical improvement, including normalization of C-reactive protein and reduction of fecal calprotectin.
    - **Long-term targets:** Endoscopic healing, histological healing, steroid-free remission, improved quality of life, and prevention of hospitalization, surgery, relapse, and disease complications.
    - **Composite targets:** Disease clearance, which combines symptomatic remission, endoscopic healing, and histological healing.
    - **Emerging monitoring tools:** Intestinal ultrasound and other non-invasive methods for early assessment of treatment response

  - **Relation to the Project**: It is relevant for defining a clinically meaningful endpoint for a future therapeutic-response prediction project. It shows that medication exposure alone—for example, whether a patient received infliximab or certolizumab—is not equivalent to treatment response. A response-prediction model should instead use a predefined outcome, such as clinical remission, reduction in fecal calprotectin, endoscopic healing, histological healing, or a composite disease-clearance endpoint at a specified follow-up time.

    However, the current HMP2/IBDMDB metadata used in this project did not provide a sufficiently clear and consistently recorded therapeutic-response endpoint. Therefore, the project was redirected toward predicting UC, CD, and nonIBD from species-level MGX metagenomic profiles.



ML models to test in this project: Random forest, gradient boosted trees (GBT)