# Dataset Characteristics

**[Notebook](exploratory_data_analysis.ipynb)**

## Dataset Information

### Dataset Source
- **Dataset Link:** [IBDMBD](https://ibdmdb.org/) 
- **Dataset Owner/Contact:** Open Access

### Dataset Characteristics

##### Clinical Metadata

- **Number of observations:** 5533 sample-level records
- **Number of metadata features:** 490
- **Data format:** Tabular CSV file
- **Main identifier:** `External ID`
- **Participant information:** Participant and sample identifiers, diagnosis, study visit, and sample type
- **Clinical variables:** Demographics, disease characteristics, medical history, disease manifestations, medications, and sample-related information

The clinical metadata table contains repeated sample-level observations from subjects. Therefore, a subject may contribute more than one sample over time or from different sample types.

##### MGX Metagenomic Features

- **Number of MGX profiles downloaded:** 1638
- **Number of species-level taxonomic features:** 578
- **Data format:** Taxonomic profile TSV files
- **Feature type:** Species-level microbial relative abundances
- **Feature representation:** One row per sample and one column per microbial species

Each MGX feature represents the relative abundance of a bacterial species in a sample. Relative abundance is expressed as the percentage or proportion of the microbial community assigned to that taxon. For example, a feature such as:

```text
k__Bacteria|p__Bacteroidetes|c__Bacteroidia|o__Bacteroidales|
f__Bacteroidaceae|g__Bacteroides|s__Bacteroides_vulgatus
```

represents the relative abundance of *Bacteroides vulgatus* in a particular sample.

The MGX feature matrix is a high-dimensional numerical tabular dataset. The first column, `sample_id`, identifies the sample, while the remaining columns contain species-level relative-abundance values. The `sample_id` column was used only to merge MGX profiles with the clinical metadata and was not used as a model predictor.

### Merged Dataset

The MGX feature matrix was joined to the clinical metadata using the `External ID` column as it provided the sample-level identifier.

- **Merged observations:** 3826 samples
- **Diagnosis classes:** CD, UC, and nonIBD
- **Model predictors:** 578 species-level MGX features
- **Target variable:** `diagnosis`

### Target Variable/Label
- **Label Name:** 'diagnosis'
- **Label Type:** Multiclass classification
- **Label Description:** Clinical diagnosis assigned to each sample.
- **Label Values:** 
  - `CD`: Crohn's disease
  - `UC`: Ulcerative colitis
  - `nonIBD`: Non-inflammatory bowel disease control 
- **Label Distribution:** 
  - `CD`: 1767 samples
  - `UC`: 1053 samples
  - `nonIBD`: 1006 samples

    CD is the largest class, followed by UC and nonIBD. Since the classes are not perfectly balanced, macro F1-score was used alongside accuracy to evaluate model performance.

### Feature Description
- **Feature (MGX):** The MGX features are numerical species-level relative-abundance measurements obtained from whole-genome shotgun metagenomic sequencing. Each row corresponds to one sample, and each species column represents the abundance of a microbial taxon in that sample.

    The MGX feature matrix contains species from several bacterial groups, including taxa from:

    - *Bacteroides*
    - *Faecalibacterium*
    - *Roseburia*
    - *Akkermansia*
    - *Ruminococcus*
    - *Alistipes*
    - *Blautia*
    - *Parabacteroides*

    These microbial features were used as predictors for the three-class diagnosis classification task.


Clinical metadata were used for exploratory analysis, sample matching, and label assignment. Diagnosis-related metadata were excluded from the MGX-only predictive model to prevent label leakage.

## Data Preprocessing

The following preprocessing steps were performed:

1. Clinical metadata were loaded from the HMP2 metadata CSV file.
2. MGX taxonomic profile files were downloaded and parsed.
3. Species-level taxa were selected using the `|s__` taxonomy marker.
4. Individual species profiles were combined into a single feature matrix.
5. MGX profiles were merged with clinical metadata using `External ID`.
6. Samples without one of the three target labels were excluded.
7. `sample_id` and other metadata columns were excluded from the MGX predictor matrix.
8. The remaining MGX features were used as numerical predictors.
9. Subject-level train/test splitting was used to prevent samples from the same subject appearing in both sets.


## Exploratory Data Analysis

The exploratory data analysis is conducted in the [exploratory_data_analysis.ipynb](exploratory_data_analysis.ipynb) notebook, which includes:

- Data loading and initial inspection
- Statistical summaries and distributions
- Missing value analysis
- Feature correlation analysis
- Data visualization and insights
- Data quality assessment
