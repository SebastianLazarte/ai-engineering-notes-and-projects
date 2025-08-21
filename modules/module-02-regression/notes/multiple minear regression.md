# 🎥 Introduction to Multiple Linear Regression

## 🎯 Learning Objectives
After studying this module, you will be able to:
- Describe **multiple linear regression (MLR)**.
- Compare **multiple linear regression** with **simple linear regression**.
- Identify **pitfalls and limitations** of MLR.

---

## 📌 1. What is Multiple Linear Regression?
- **Extension of Simple Linear Regression (SLR):**
  - **SLR**: uses **one** independent variable (feature) to predict an outcome.
  - **MLR**: uses **two or more** independent variables to predict the dependent variable.
- The model is expressed as a **linear combination**:
  
  \[
  \hat{y} = \theta_0 + \theta_1 x_1 + \theta_2 x_2 + ... + \theta_n x_n
  \]
  
  - **θ₀ (intercept)**: baseline when all features = 0.  
  - **θᵢ (coefficients)**: represent the influence of each feature.  
  - Can be represented with matrices for easier computation.

---

## 📌 2. Why Use MLR?
- Captures **multiple factors** affecting the outcome.  
- Measures the **strength and direction** of each variable’s impact.  
- Allows **prediction for unseen data**.  
- Supports **what-if analysis** (e.g., “What if BMI increases by 2 units?”).

---

## 📌 3. Applications
- **Automobiles**: predict CO₂ emissions from engine size, cylinders, and fuel consumption.  
- **Education**: model how revision time, attendance, anxiety, and gender affect exam performance.  
- **Healthcare**: estimate blood pressure changes based on BMI or lifestyle changes.  
- **What-if scenarios**: simulate effects of changing inputs while holding others constant.

---

## 📌 4. Comparison with Simple Linear Regression
- **SLR**: outcome = line in 2D space (y vs. x).  
- **MLR**: outcome = plane (2 predictors) or hyperplane (more than 2).  
- Both models estimate coefficients by minimizing **mean squared error (MSE)**.  

---

## 📌 5. Pitfalls of Multiple Linear Regression
1. **Overfitting**  
   - Adding too many predictors can make the model memorize training data.  
   - Poor generalization to new data.

2. **Multicollinearity**  
   - When predictors are strongly correlated, they are not independent.  
   - This makes coefficient interpretation unreliable.

3. **Unrealistic What-If Scenarios**  
   - Changing one variable while keeping correlated ones fixed may be impossible.  
   - Example: Increasing engine size without changing fuel consumption.

4. **Extrapolation Risks**  
   - Predicting outside the range of training data can be highly inaccurate.

---

## 📌 6. Handling Categorical Variables
- Convert categories into numbers (encoding):
  - **Binary variable**: manual = 0, automatic = 1.  
  - **Multi-class**: create new Boolean/dummy variables for each class.  

---

## 📌 7. Estimating the Parameters
Two common methods:
1. **Ordinary Least Squares (OLS)**  
   - Uses linear algebra to find coefficient values that minimize MSE.  
   - Works well for small/medium datasets.  

2. **Optimization (Gradient Descent)**  
   - Iteratively adjusts coefficients to reduce error.  
   - Preferred for very large datasets.  

---

## 📌 8. Key Takeaways
- Multiple Linear Regression models an outcome using **several predictors**.  
- It provides both **prediction power** and **explanatory insight**.  
- Works best when variables are **independent, relevant, and linear in effect**.  
- Needs careful **variable selection** to avoid redundancy and overfitting.  
- Most common estimation methods: **Ordinary Least Squares** and **Gradient Descent**.  

---
