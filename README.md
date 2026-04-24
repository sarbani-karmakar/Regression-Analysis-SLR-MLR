# Regression Analysis
## Overview
Theoretical questions and answers covering Simple Linear Regression (SLR)
and Multiple Linear Regression (MLR) concepts, as part of the
Accio-ISB data analytics program.

## Result: 9.8/10

---

## Q1: Explain the core concept of Simple Linear Regression (SLR). What are you trying to achieve with an SLR model?

**Answer:** The core concept of SLR is to model the relationship between
two variables by fitting a straight line to the observed data. It involves
one independent variable (X) and one dependent variable (Y). The model is
represented by: Y = β0 + β1X + ε, where β0 is the Y-intercept, β1 is the
slope, and ε is the random error term. The goal is to find the best fitting
line that minimizes the overall error between predicted and actual values.
This allows us to:
- Quantify how a unit change in X affects Y
- Predict/forecast the value of Y for a given value of X

---

## Q2: Define Intercept, Coefficient, and R-squared in SLR

**Intercept (β0):** The predicted value of Y when X = 0. It represents the
starting point of the regression line on the Y-axis. Its practical meaning
depends on whether X = 0 is logical within the data range.

**Coefficient (β1):** The average change in Y for a 1-unit increase in X.
A positive β1 means Y increases as X increases; a negative β1 means Y
decreases as X increases.

**R-squared (R²):** The proportion of total variation in Y explained by X.
For example, R² = 0.80 means 80% of Y's variability is explained by its
linear relationship with X. The remaining 20% is unexplained random error.

---

## Q3: Case Study — Exam Score vs Study Hours

**Regression Output:**
- Intercept (β0): 65.2
- Coefficient for Study_Hours (β1): 4.5
- R-squared (R²): 0.78

**(I) Regression Equation:**
Ŷ = 65.2 + 4.5 × (Study_Hours)

**(II) Interpret the Intercept (65.2):**
A student who studied 0 hours is predicted to score 65.2. This represents
the expected baseline score from prior knowledge, guesswork, or intuition.

**(III) Interpret the Coefficient (4.5):**
For each additional hour of studying, the predicted exam score increases by
4.5 points. A student who studies 2 more hours than another is predicted to
score 9 points higher.

**(IV) Interpret R-squared (0.78):**
78% of the variation in exam scores is explained by study hours. The
remaining 22% is due to other factors such as prior knowledge, test-taking
skills, or random chance.

**(V) Prediction for 8 hours of study:**
Ŷ = 65.2 + 4.5(8) = 65.2 + 36 = **101.2**

---

## Q4: What is a Dummy Variable? Why are they necessary?

**Answer:** A dummy variable is a numerical variable (0 or 1) used to
represent categorical data in regression models. For example, for "Gender":
1 = Female, 0 = Male.

Dummy variables are necessary because regression models require numerical
input. They allow meaningful categorical predictors (like city, product
type, or marital status) to be included by converting them into a numeric
format the model can process, and are used to estimate a different intercept
for each group.

---

## Q5: How many dummy variables for "Season" (Spring, Summer, Autumn, Winter)?

**Answer:** 3 dummy variables are needed. For k categories, we need (k-1)
dummy variables. One category is left out as the reference/baseline to
avoid multicollinearity.

With 4 seasons (k=4), we need 4-1 = 3 dummy variables:
- **D1 (Summer):** 1 if Summer, 0 otherwise
- **D2 (Autumn):** 1 if Autumn, 0 otherwise
- **D3 (Winter):** 1 if Winter, 0 otherwise

Spring is the reference category (when D1 = D2 = D3 = 0). All other
seasons are interpreted as differences from the Spring baseline.

---

## Q6: How does coefficient interpretation change from SLR to MLR?

**Simple Linear Regression (1 predictor):**
- Equation: Y = β0 + β1X1 + ε
- Interpretation: Average change in Y for a 1-unit increase in X1
- Represents the **total effect** of X1 on Y, including effects channelled
  through other correlated variables

**Multiple Linear Regression (2+ predictors):**
- Equation: Y = β0 + β1X1 + β2X2 + … + ε
- Interpretation: Average change in Y for a 1-unit increase in X1,
  **holding all other variables constant**
- Represents the **partial/direct effect** of X1 on Y, isolated from
  other predictors

In summary: SLR gives the total marginal effect; MLR gives the partial
effect after adjusting for all other variables in the model.

---

## Q7: Explain "Ceteris Paribus" and its importance in MLR

**Answer:** Ceteris Paribus means "all other things being equal" or
"holding other factors constant." It is the foundational assumption for
interpreting coefficients in a multiple regression model.

---

## Q8: Case Study: Predicting House Prices

**Regression Output:**
- Intercept: 50,000
- Coefficient for Sqft: 150
- Coefficient for Bedrooms: 25,000
- Coefficient for Age: -1,200

**(I) Regression Equation:**
Ŷ = 50,000 + 150(Sqft) + 25,000(Bedrooms) − 1,200(Age)

**(II) Coefficient for Sqft (150):**
For each additional square foot, the predicted house price increases by
₹150, holding bedrooms and age constant (Ceteris Paribus).

**(III) Coefficient for Bedrooms (25,000):**
For each additional bedroom, the predicted house price increases by ₹25,000,
holding square footage and age constant (Ceteris Paribus).

**(IV) Coefficient for Age (-1,200):**
For each additional year of age, the predicted house price decreases by
₹1,200, holding sqft and bedrooms constant. The negative value reflects
depreciation due to wear and tear, aging components, and outdated styles.
