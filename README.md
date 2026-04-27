1. Approach
The objective of this project was to build a predictive model for Titanic survival by transforming raw data into meaningful features. The workflow followed these major steps:
Exploratory Data Analysis (EDA): Identifying patterns and missingness in the data.
Data Cleaning: Handling missing values, outliers, and inconsistencies.
Feature Engineering: Creating new variables to capture social and family dynamics.
Feature Selection: Identifying the most impactful features using statistical and machine learning methods

2. Data Cleaning Decisions
Missing Values: * Age: Imputed with the median to maintain the distribution without being influenced by extreme outliers.
Embarked: Imputed with the mode (most frequent value).
Cabin: Dropped due to a high percentage of missing values (over 70%)
Outliers: Capped the Fare and Age columns using the Interquartile Range (IQR) method to prevent extreme values from biasing the model.
Consistency: Standardized the Sex column to ensure uniform values (male/female).

3. Features Engineered
Several new features were derived to improve model performance:
FamilySize: Created by adding SibSp (siblings/spouses) and Parch (parents/children) plus the passenger themselves.
IsAlone: A binary flag (1 if traveling solo, 0 if with family).
Title: Extracted from the Name column to capture social status (e.g., Mr, Mrs, Master).
Deck: Extracted from the Cabin column to identify the passenger's location on the ship.
AgeGroups: Categorized ages into 'Child', 'Teen', 'Adult', and 'Senior'.
FarePerPerson: Normalized the ticket cost relative to the number of family members.
Log Transformations: Applied a log transform to Fare to normalize its heavily skewed distribution

4. Key Findings & Feature Selection
Using a Random Forest Classifier and Correlation Analysis, the following observations were made:
Top Predictors: Title, Sex, and Fare_log were the most significant features in predicting survival.
Redundancy: Features like SibSp and Parch were dropped because they were highly correlated with the new FamilySize feature.
Impact of Transformation: Normalizing Fare via log transformation significantly improved the model's
ability to process wealth-related data.

6. Instructions to Run
Clone the repository: git clone https://github.com/vohtieno/AI_assignment_2.git.
Install dependencies: pip install -r requirements.txt.
Run Notebooks: Open the files in the notebooks/ folder for step-by-step exploration.
Run Scripts: Execute the Python files in the scripts/ folder for the modularized pipeline.

