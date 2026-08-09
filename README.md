#  NBA Home-Court Advantage During COVID-19

### An R Data Analysis & Predictive Modeling Project

This project investigates how the COVID-19 pandemic affected **home-court advantage and game outcomes in the NBA** using game-level data from the 2012–2024 seasons.

Using **R, tidyverse, ggplot2, feature engineering, and linear regression**, I analyzed differences in home and away performance under normal and COVID-affected game conditions and developed predictive models for NBA point differential.

---

##  Project Overview

Home-court advantage has traditionally played an important role in NBA games. During the COVID-19 pandemic, however, games were played under unusual conditions including restricted attendance and limited or absent crowds.

This project explores whether those conditions changed the advantage normally experienced by home teams.

### Questions Explored

- Did home-court advantage decrease during COVID-affected games?
- How did home and away teams perform under COVID vs. normal conditions?
- How did shooting efficiency relate to winning and scoring margin?
- Can shooting efficiency, game location, and COVID status predict point differential?
- Does including COVID status improve predictive performance?

---

##  Key Findings

- **COVID-19 softened, but did not eliminate, home-court advantage.**
- Home teams continued to outperform away teams during COVID-affected games, but the difference in scoring margins became smaller.
- **Shooting efficiency (eFG%) and game location** were useful predictors of point differential.
- Including **COVID game status** in the regression model slightly improved predictive performance.
- Overall, pandemic conditions made NBA outcomes less tilted toward the home team while still leaving a measurable home-court advantage.

---

##  Technologies & Skills

**Language:** R

**Libraries:**
- tidyverse
- dplyr
- ggplot2
- tidyr
- modelr
- broom
- lubridate
- forcats
- ggrepel

**Techniques:**
- Data Cleaning
- Exploratory Data Analysis
- Feature Engineering
- Data Visualization
- Linear Regression
- Interaction Effects
- Train / Validation / Test Splitting
- RMSE Model Evaluation

---

##  Data Preparation & Feature Engineering

The raw NBA dataset was transformed into an analysis-ready dataset using several preprocessing steps.

These included:

- Creating **Home/Away classifications**
- Converting game results into descriptive Win/Loss categories
- Identifying **COVID vs. normal games**
- Standardizing historical franchise names
- Creating season-year variables
- Creating scoring-margin categories such as close wins and blowout wins
- Converting categorical variables into factors
- Removing unnecessary variables

The cleaned dataset was then divided into:

- **60% Training Data**
- **20% Validation Data**
- **20% Test Data**

This allowed model development and selection to occur without using the final test set.

---

##  Exploratory Data Analysis

Several visualizations were created using **ggplot2** to investigate relationships between game performance, location, and COVID conditions.

### Shooting Efficiency vs. Win Percentage

Examined the relationship between effective field goal percentage (**eFG%**) and win percentage for home and away teams across COVID and normal games.

### Shooting Efficiency by Location

Compared the distribution of shooting efficiency between home and away teams under different game conditions using violin and box plots.

### Average Point Differential

Compared average scoring margins for home and away teams during COVID and non-COVID games to investigate changes in home-court advantage.

---

##  Predictive Modeling

Linear regression models were developed to predict:

**Point Differential (PLUS_MINUS)**

using variables including:

- Effective Field Goal Percentage (eFG%)
- Game Location
- COVID Game Status

### Model 1 — Shooting Efficiency & Location

Three specifications were compared:

```text
PLUS_MINUS ~ EFG_PCT * LOCATION
PLUS_MINUS ~ EFG_PCT + LOCATION
PLUS_MINUS ~ EFG_PCT
```

This tested whether the relationship between shooting efficiency and point differential differed between home and away games.

### Model 2 — Adding COVID Status

COVID game status was then incorporated:

```text
PLUS_MINUS ~ EFG_PCT * LOCATION + COVID_FLAG
PLUS_MINUS ~ EFG_PCT + LOCATION + COVID_FLAG
PLUS_MINUS ~ EFG_PCT * LOCATION * COVID_FLAG
```

Models were compared using **validation RMSE** to determine whether additional complexity improved predictive performance.

---

##  Model Evaluation

The strongest candidate models were refitted using the combined training and validation datasets.

Final performance was evaluated on the **held-out test set using Root Mean Squared Error (RMSE)**.

This approach allowed the models to be evaluated on data that had not been used during training or model selection.

Residual plots and residual density distributions were also used to assess model behavior and compare prediction errors.

---

##  What I Learned

This project strengthened my ability to work through the complete data analysis workflow, including:

- Transforming raw data into an analysis-ready format
- Engineering meaningful features from existing variables
- Exploring large datasets through visualization
- Translating research questions into statistical models
- Comparing models using validation data
- Evaluating predictive performance on unseen test data
- Communicating statistical results through visualizations and written conclusions

---

##  Dataset

The analysis uses the **NBA Data 2012–2024** dataset created by Kevin Pickelman and published on Kaggle.

The dataset contains game-level NBA statistics used to analyze team performance, shooting efficiency, scoring margins, and game outcomes.

---

##  Author

**Jasneet Gill**  
Data Science Student — Wilfrid Laurier University

Interested in data analysis, predictive modeling, machine learning, and applying data science to real-world problems.
