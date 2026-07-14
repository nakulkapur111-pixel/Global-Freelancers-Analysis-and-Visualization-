# Global-Freelancers-Analysis-and-Visualization-
# Global Freelancers Data Analysis

## Project Overview

This project focuses on performing an end-to-end data analysis on a global freelancers dataset obtained from Kaggle. The objective was to clean inconsistent and missing data, perform exploratory data analysis (EDA), generate meaningful business insights, and visualize important trends that can help understand the global freelancing market.

The project demonstrates the complete data analysis workflow using Python and its data science ecosystem.

---

## Objectives

- Import and understand the dataset.
- Clean inconsistent and missing values.
- Standardize categorical and numerical data.
- Perform exploratory data analysis.
- Generate meaningful business insights.
- Visualize trends using charts.
- Build a composite performance score to identify top-performing freelancers.

---

## Dataset

**Source:** Kaggle - Global Freelancers Raw Dataset

The dataset contains information about freelancers including:

- Age
- Gender
- Country
- Primary Skill
- Years of Experience
- Hourly Rate
- Client Satisfaction
- Rating
- Active Status

Since the dataset is intentionally raw, it contains several inconsistencies such as:

- Missing values
- Mixed data formats
- Different representations of the same values
- Numerical values stored as strings
- Unnecessary characters

These issues were resolved during the data cleaning phase.

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

The project begins by importing all the necessary Python libraries for data manipulation and visualization.

Libraries used:

- pandas
- numpy
- matplotlib
- seaborn
- kagglehub
- os

These libraries were used for:

- Loading the dataset
- Cleaning data
- Numerical operations
- Visualization
- Downloading the dataset directly from Kaggle

---

## Step 2: Load Dataset

The dataset was downloaded using KaggleHub and imported into a Pandas DataFrame.

After loading:

- Displayed the dataset
- Verified successful import
- Examined the available columns

---

## Step 3: Initial Data Exploration

Before cleaning the data, an initial exploration was performed.

The following checks were carried out:

- Displayed unique values of every column
- Checked data types
- Counted missing values
- Viewed descriptive statistics

This helped identify:

- Missing values
- Incorrect data types
- Duplicate categorical values
- Columns requiring cleaning

---

# Data Cleaning

A significant portion of the project involved cleaning the dataset.

## 1. Cleaning Active Status

The **is_active** column contained multiple representations such as:

- True
- False
- yes
- no
- Y
- N
- Missing values

These were standardized into binary values:

- 1 → Active
- 0 → Inactive

The column was then converted into a numeric datatype.

---

## 2. Cleaning Gender

The gender column contained inconsistent values such as:

- M
- m
- male
- Male
- MALE
- F
- f
- Female
- FEMALE

All values were standardized into only two categories:

- M
- F

This ensured consistency throughout the analysis.

---

## 3. Handling Missing Years of Experience

Some freelancers had missing experience values.

These missing values were replaced with the average years of experience of the dataset.

This preserved the dataset while minimizing data loss.

---

## 4. Handling Missing Age Values

Missing age values were replaced using the mean age of the dataset.

This allowed age-based analyses to remain complete.

---

## 5. Cleaning Client Satisfaction

The client satisfaction column contained numbers enclosed with extra characters.

Example:

```
(72)
```

Using regular expressions:

- Numerical values were extracted
- Converted into numeric datatype
- Missing values replaced with the column mean

---

## 6. Cleaning Hourly Rate

Hourly rate values were also stored as strings containing non-numeric characters.

The cleaning process involved:

- Extracting numeric values
- Converting to numeric datatype
- Replacing missing values with the average hourly rate

---

## 7. Cleaning Rating

Missing ratings were replaced with the average rating.

This ensured every freelancer could be included in performance analysis.

---

# Exploratory Data Analysis

After cleaning, several business questions were answered using visualizations.

---

## Analysis 1: Most Common Freelancer Skills

A frequency analysis was performed on the **Primary Skill** column.

### Insight

- The top five skills represent the largest share of freelancers.
- These skills indicate the highest demand within the freelance marketplace.
- Businesses can focus recruitment around these skill categories.

Visualization:

- Line Chart

---

## Analysis 2: Countries with the Highest Number of Freelancers

The dataset was grouped by country.

A bar chart was created to compare freelancer distribution across countries.

<img width="368" height="264" alt="image" src="https://github.com/user-attachments/assets/718fc37f-6415-4181-8a7a-f6811b612bc6" />


### Insight

- Some countries contribute significantly more freelancers than others.
- These countries represent mature freelance ecosystems.
- Businesses looking to hire globally can prioritize talent acquisition in these regions.

Visualization:

- Bar Chart

---

## Analysis 3: Relationship Between Experience and Earnings

Freelancers were categorized according to years of experience.

Experience levels included:

- Entry Level
- Junior Level
- Senior Level
- Supervisor

Hourly earnings were then compared across these categories.

### Insight

- More experienced freelancers generally command higher hourly rates.
- Experience remains one of the strongest indicators of earning potential.
- Investing in skill development can directly improve freelancer income.

Visualization:

- Comparison Chart

---

## Analysis 4: Activity Distribution by Age and Skill

The project examined freelancer activity status across:

- Age
- Primary Skill

A histogram and pie chart were used.

### Insight

- Certain age groups remain more active than others.
- Some skills exhibit much higher active freelancer percentages.
- Businesses can focus marketing efforts on these highly active skill segments.

Visualization:

- Histogram
- Pie Chart

---

## Analysis 5: Composite Performance Score

Instead of relying on a single metric, a custom performance score was created.

The score used weighted contributions from:

| Metric | Weight |
|---------|---------|
| Rating | 30% |
| Client Satisfaction | 30% |
| Years of Experience | 20% |
| Hourly Rate | 20% |

This generated a composite score representing overall freelancer performance.

### Insight

- High-performing freelancers consistently score well across multiple metrics.
- Composite scoring provides a more balanced evaluation than individual ratings alone.
- This approach can support hiring and talent-ranking decisions.

---

## Correlation Analysis

A correlation matrix was generated between:

- Years of Experience
- Hourly Rate
- Client Satisfaction

A heatmap was used for visualization.

### Insight

- Positive correlations indicate variables that tend to increase together.
- The analysis helps identify which freelancer characteristics influence earnings and client satisfaction.
- Correlation provides useful guidance for predictive modeling and business decision-making.

Visualization:

- Heatmap

---

# Key Insights

- Freelancer data often contains inconsistent formatting that must be cleaned before analysis.
- Experience generally contributes to higher hourly earnings.
- Certain countries dominate the freelance marketplace.
- A few skills account for a large proportion of freelancers.
- Composite performance scores provide a more reliable ranking than single performance metrics.
- Correlation analysis helps understand relationships between experience, earnings, and client satisfaction.

---

# Challenges Faced

- Missing values across multiple columns
- Mixed categorical formats
- Numeric values stored as text
- Special characters in numerical fields
- Standardizing inconsistent labels
- Selecting meaningful business questions for analysis

---

# Learning Outcomes

This project strengthened practical skills in:

- Data Cleaning
- Data Wrangling
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Data Visualization
- Business Insight Generation
- Correlation Analysis
- Working with real-world messy datasets
- Python data analysis libraries

---

# Future Scope

This project can be extended in several ways:

- Build machine learning models to predict freelancer hourly rates based on experience, ratings, skills, and country.
- Develop an interactive dashboard using Power BI, Tableau, or Streamlit for real-time data exploration.
- Perform time-series analysis if historical freelancer activity data becomes available.
- Conduct skill demand forecasting to identify emerging freelance technologies and domains.
- Apply clustering algorithms to segment freelancers based on experience, earnings, and performance.
- Incorporate additional datasets such as project success rates or client reviews for deeper analysis.
- Deploy the analysis as a web application to allow users to upload and analyze their own freelancer datasets.

---

# Conclusion

This project demonstrates a complete end-to-end data analytics workflow using Python. Starting from a raw dataset, the project involved cleaning inconsistent data, handling missing values, performing exploratory data analysis, generating business insights, and visualizing key trends. The final analysis provides valuable understanding of freelancer demographics, earning patterns, skill distribution, and performance evaluation while showcasing practical data analysis techniques applicable to real-world business problems.
