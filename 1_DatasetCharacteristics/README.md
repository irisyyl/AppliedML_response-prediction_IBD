# Dataset Characteristics

**[Notebook](exploratory_data_analysis.ipynb)**

## Dataset Information

### Dataset Source
- **Dataset Link:** [IBDMBD](https://ibdmdb.org/) 
- **Dataset Owner/Contact:** Open Access

### Dataset Characteristics
- **Number of Observations:** Total number of samples: 5533
- **Number of Features:** Total number of features: 490 

### Target Variable/Label
- **Label Name:** 'diagnosis'
- **Label Type:** Classification
- **Label Description:** Predict 'diagnosis' based on clinical features. 
- **Label Values:** [For classification: list of classes and their meanings. For regression: range of values. For other tasks: describe the label structure]
- **Label Distribution:** [Brief description of class balance for classification or value distribution for regression]

### Feature Description
A range of features are used to predict the label. Features include: 

- **Feature 1 (Medication):** 
'Antibiotics', 'Chemotherapy', 'Immunosuppressants (e.g. oral corticosteroids)','Lomotil', 'Dipentum (olsalazine)', 'Rowasa enemas (mesalamine enemas)', 'Canasa suppositories (mesalamine suppositories)', 'Flagyl (Metronidazole)', 'Cipro (Ciprofloxin)', 'Xifaxin (rifaxamin)', 'Levaquin', 'Other Antibiotic:', 'Prednisone', 'Entocort (Budesonide)', 'Imodium', 'Solumedrol (Medrol)','IV steroids','Cortenemas, Cortifoam, Proctofoam','Azathioprine (Imuran, Azasan)','Methotrexate','Mercaptopurine (Purinethol, 6MP)','VSL #3','FOS','Remicade (Infliximab)','Humira (Adalimumab)', 'DTO', 'Cimzia (Certlizumab)','Tysabri (Natalizumab)','Asacol (mesalamine)','Pentasa (mesalamine)','Lialda (mesalamine)','Apriso (mesalamine)','Colozal (balasalizide)','Sulfasalizine (Azulfidine)'
[Description of what this feature represents, data type, and any relevant details]

- **Feature 2 (Montreal classification):** 
'Age at diagnosis (A)', 'baseline_montreal_location', 'Location (L) prior to first surgery', 'Behavior (B)', 'Extent (E)'
[Description of what this feature represents, data type, and any relevant details]

- **Feature Group (group_name):** [Description of a group of related features]

## Exploratory Data Analysis

The exploratory data analysis is conducted in the [exploratory_data_analysis.ipynb](exploratory_data_analysis.ipynb) notebook, which includes:

- Data loading and initial inspection
- Statistical summaries and distributions
- Missing value analysis
- Feature correlation analysis
- Data visualization and insights
- Data quality assessment
