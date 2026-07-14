# Global Freelancers Data Analysis Using Python

# Project Overview

This project presents a complete end-to-end Exploratory Data Analysis (EDA) workflow using Python on a real-world freelancers dataset. The primary objective was to clean a raw dataset, transform inconsistent and missing data into a usable format, perform exploratory analysis, and generate actionable insights through visualizations. The project demonstrates the practical application of data cleaning, preprocessing, feature engineering, statistical analysis, and data visualization techniques that are commonly used in real-world data analytics projects.

# Problem Statement
Raw datasets collected from multiple sources often contain missing values, inconsistent formatting, duplicate representations, and incorrect data types. These issues reduce the quality of analysis and lead to misleading insights.

# Objective
The objective of this project was to:

- Clean and preprocess the freelancer dataset.
- Standardize categorical and numerical variables.
- Explore patterns within the data.
- Answer important business questions using visualizations.
- Identify relationships among key freelancer attributes.
  
# Dataset

The dataset contains information about freelancers working across different countries.

### Features Included

- Age
- Gender
- Country
- Primary Skill
- Years of Experience
- Hourly Rate (USD)
- Client Satisfaction
- Rating
- Active Status

Since the dataset is intentionally raw, it contains several inconsistencies including missing values, mixed formats, incorrect data types, and non-standard categorical labels.

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- KaggleHub
- Jupyter Notebook

---

# Project Workflow

## Step 1: Import Required Libraries

The project begins by importing all the required Python libraries.

Libraries used:

- Pandas
- NumPy
- Matplotlib
- Seaborn
- KaggleHub
- OS

These libraries were used for downloading the dataset, cleaning data, performing numerical operations, and creating visualizations.

---

## Step 2: Download and Load the Dataset

The freelancer dataset was downloaded directly from Kaggle using KaggleHub. After downloading, it was loaded into a Pandas DataFrame for analysis. This step ensured that the dataset was successfully imported and ready for preprocessing.

---

## Step 3: Initial Data Exploration

Before cleaning the dataset, several exploratory checks were performed to understand its structure and quality.

The following operations were carried out:

- Displayed all unique values in every column.
- Examined data types using `dtypes`.
- Identified missing values using `isnull().sum()`.
- Generated summary statistics using `describe()`.

### Purpose

These checks helped identify:

- Missing values
- Incorrect data types
- Duplicate category names
- Columns requiring preprocessing

---

# Data Cleaning

The dataset contained several inconsistencies that were corrected before performing any analysis.

---

## Cleaning the Active Status Column

The **is_active** column contained different representations of the same information such as:

- True
- False
- yes
- no
- Y
- N
- Missing values

These were standardized into binary values:

- 1 = Active
- 0 = Inactive

The column was then converted into a numeric datatype.

### Why this was necessary

A binary format simplifies filtering, aggregation, and visualization while eliminating ambiguity.

---

## Cleaning the Gender Column

The gender column contained multiple representations including:

- male
- Male
- MALE
- m
- female
- Female
- FEMALE
- f

These values were standardized into:

- M
- F

### Why this was necessary

Consistent categorical values prevent duplicate groups from appearing during analysis.

---

## Handling Missing Years of Experience

Some freelancers had missing values in the experience column.

These missing values were replaced with the average years of experience.

### Why this was necessary

Replacing missing values preserved the dataset while maintaining reasonable estimates instead of removing observations.

---

## Handling Missing Age Values

Missing age values were replaced using the mean age of all freelancers.

### Why this was necessary

This ensured that age-based analyses remained complete without reducing the dataset size.

---

## Cleaning the Client Satisfaction Column

The client satisfaction values contained unnecessary characters and were stored as strings.

Example:

```
(72)
```

Regular expressions were used to extract only the numeric values.

The cleaned values were then converted into numeric format, and missing values were replaced using the average client satisfaction score.

### Why this was necessary

This enabled mathematical calculations and statistical analysis.

---

## Cleaning the Hourly Rate Column

Hourly rate values were also stored as strings containing unwanted characters.

The following steps were performed:

- Extracted numeric values using regular expressions.
- Converted the column into numeric datatype.
- Replaced missing values with the average hourly rate.

### Why this was necessary

Cleaning this column allowed meaningful calculations such as averages, correlations, and comparisons.

---

## Cleaning the Rating Column

Missing ratings were replaced using the average rating.

### Why this was necessary

This ensured that every freelancer could be included in the performance analysis.

---

# Exploratory Data Analysis

After preprocessing the dataset, several business questions were explored.

---

# Analysis 1: Top Five Skills Among Freelancers

The dataset was grouped according to the **Primary Skill** column to identify the five most common freelancer skills.

A visualization was created to compare the popularity of these skills.

### Insight

- A small number of skills account for a large share of freelancers.
- These skills indicate the areas where freelance participation is highest.
- Organizations can prioritize hiring within these domains based on market availability.
<img width="547" height="465" alt="image" src="https://github.com/user-attachments/assets/4432ba5b-bebb-43c0-bd63-b74610c3731a" />

---

# Analysis 2: Countries with the Highest Number of Freelancers

The number of freelancers from each country was calculated and visualized.

### Insight

- Some countries contribute significantly more freelancers than others.
- These countries represent mature freelance ecosystems.
- Businesses looking to hire globally can prioritize these regions for talent acquisition.
<img width="480" height="482" alt="image" src="https://github.com/user-attachments/assets/9cfa97ec-82b1-492c-811d-9bd5cf299d84" />

---

# Analysis 3: Does Experience Influence Freelancer Earnings?

Freelancers were categorized according to their years of experience.

Experience categories included:

- Entry Level
- Junior Level
- Senior Level
- Supervisor

The average hourly rate for each category was then compared.

### Insight

- Hourly rates generally increase with experience.
- More experienced freelancers are able to command higher compensation.
- Experience appears to be one of the strongest indicators of earning potential.
<img width="449" height="465" alt="image" src="https://github.com/user-attachments/assets/29ff1caa-4280-48c7-a0af-3d9f1a402946" />

---

# Analysis 4: Identifying Top-Performing Freelancers

A composite performance score was created to evaluate freelancers more comprehensively.

The score was calculated using the following weights:

| Metric | Weight |
|---------|---------:|
| Rating | 30% |
| Client Satisfaction | 30% |
| Years of Experience | 20% |
| Hourly Rate | 20% |

### Insight

- Evaluating freelancers using multiple metrics provides a more balanced assessment than relying on ratings alone.
- High-performing freelancers consistently perform well across several performance indicators.
- Such scoring methods can assist organizations during recruitment and talent evaluation.
<img width="499" height="449" alt="image" src="https://github.com/user-attachments/assets/c503f135-f9a0-40c0-851b-0d051e2a1d72" />

---

# Analysis 5: Does Age Influence Freelancer Activity?

A histogram was created to compare freelancer age with active and inactive status.

### Insight

- Freelancer activity varies across different age groups.
- Certain age ranges contain a higher proportion of active professionals.
- Understanding these patterns helps identify the most engaged workforce segments.
<img width="382" height="262" alt="image" src="https://github.com/user-attachments/assets/36e1d0d0-a253-43a8-8bb7-7c388999baaa" />

---

# Analysis 6: Active Freelancer Percentage Across Skills

The percentage of active freelancers was calculated for each primary skill.

### Insight

- Some skills have noticeably higher active participation.
- High activity percentages may indicate stronger market demand or better employment opportunities.
- Businesses can use this information to focus on highly active talent pools.
<img width="662" height="558" alt="image" src="https://github.com/user-attachments/assets/b94b2e8f-9651-46f4-90f3-6581aa4c9313" />

---

# Analysis 7: Correlation Analysis between Freelancer Hourly Attributes

A correlation matrix was generated using the following variables:

- Years of Experience
- Hourly Rate (USD)
- Client Satisfaction

The relationships among these variables were visualized using a heatmap.

### Insight

- Positive correlations indicate variables that tend to increase together.
- The heatmap provides a quick understanding of how experience, earnings, and client satisfaction interact.
- Correlation analysis serves as a useful starting point for predictive modeling and further statistical analysis.
<img width="772" height="819" alt="image" src="https://github.com/user-attachments/assets/19e7dd60-2a4f-4503-a7ef-8c97a986ccef" />

---

# Key Insights

- Cleaning raw data is an essential step before conducting meaningful analysis.
- Standardizing categorical variables improves consistency and reliability.
- Replacing missing values helps preserve valuable information without significantly affecting overall trends.
- Experienced freelancers generally earn higher hourly rates.
- A small number of skills dominate the freelancer marketplace.
- Certain countries contribute a larger share of freelancers.
- Activity levels differ across age groups and skill categories.
- Composite performance scoring offers a more holistic evaluation of freelancer performance.
- Correlation analysis helps understand relationships among important business variables.

---

# Challenges Faced

Throughout the project, several real-world data quality issues were addressed, including:

- Missing values
- Incorrect data types
- Duplicate categorical labels
- Numeric values stored as text
- Unwanted special characters
- Standardizing inconsistent formatting

Successfully resolving these challenges significantly improved the quality of the analysis.

---

# Skills Demonstrated

This project demonstrates practical experience in:

- Data Collection
- Data Cleaning
- Data Preprocessing
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Data Visualization
- Correlation Analysis
- Statistical Thinking
- Business Insight Generation
- Python Programming using Pandas and NumPy

---

# Future Scope

This project can be extended in several ways to create more advanced analytical solutions:

- Develop machine learning models to predict freelancer hourly rates based on experience, skills, ratings, and client satisfaction.
- Build an interactive dashboard using Power BI, Tableau, or Streamlit for dynamic data exploration.
- Apply clustering algorithms to segment freelancers based on skills, earnings, and experience.
- Perform predictive analytics to identify the factors contributing most to freelancer success.
- Incorporate additional datasets such as project completion rates, client reviews, and project categories to improve the analysis.
- Conduct trend analysis using historical freelancer data to study changes in the freelance market over time.
- Build recommendation systems that match freelancers with suitable projects based on their profiles and performance.
- Perform geographic analysis to understand regional differences in freelancer earnings and specialization.

---

# Conclusion

This project demonstrates a complete end-to-end data analytics workflow using Python, beginning with a raw freelancer dataset and progressing through data cleaning, preprocessing, exploratory analysis, visualization, and business insight generation. The project highlights the importance of preparing high-quality data before analysis and demonstrates how meaningful insights can be extracted through structured exploration. The techniques used in this project closely reflect the workflow followed by data analysts in industry and provide a strong foundation for advanced analytics and machine learning projects.
