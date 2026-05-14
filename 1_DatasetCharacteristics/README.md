# Dataset Characteristics

**[Notebook](exploratory_data_analysis.ipynb)**

## Dataset Information

### Dataset Source
- **Dataset Link:** https://github.com/yawgmoth/HanabiData
- **Dataset Owner/Contact:** Markus Eger https://github.com/yawgmoth

### Dataset Characteristics
- **Number of Observations:** 2040
- **Number of Features:** 50

### Target Variable/Label
- **Label Name:** final_score
- **Label Type:** Regression
- **Label Description:** End score of the game
- **Label Values:** Integer number between 0 and 25
- **Label Distribution:**
    - bimodal: two distinct peaks -> one around a score of 6-7 and a larger one between 15 and 19
    - negative skewness: data is left-skewed -> majority of games result in higher scores
    - scores span full range from 0 to 24 -> diverse dataset that includes early failures and near-perfect games
    - dip around score of 10-12 suggests "threshold" where games either stabilize into ghi-scoring rounds or collapse early

### Feature Description
[Provide a brief description of each feature or group of features in your dataset. If you have many features, group them logically and describe each group. Include information about data types, ranges, and what each feature represents.]

**Example format:**
- **Feature 1 (feature_name):** [Description of what this feature represents, data type, and any relevant details]
- **Feature 2 (feature_name):** [Description of what this feature represents, data type, and any relevant details]
- **Feature Group (group_name):** [Description of a group of related features]

## Exploratory Data Analysis

The exploratory data analysis is conducted in the [exploratory_data_analysis.ipynb](exploratory_data_analysis.ipynb) notebook, which includes:

- Data loading and initial inspection
- Statistical summaries and distributions
- Missing value analysis
- Feature correlation analysis
- Data visualization and insights
- Data quality assessment
