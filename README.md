Project Overview

  The primary objective is to identify which socioeconomic and psychological factors—such as GDP, social support, and perceptions of corruption—most significantly impact a nation's happiness level. The analysis follows a standard statistical workflow: data cleaning, initial model building, diagnostic testing, and model optimization through parsimony.

Dataset Description

  The dataset includes observations from 166 different countries over a 16-year period. Key variables analyzed include:

    Life Ladder: The target variable (happiness score).

    Log GDP per capita: Economic output adjusted for purchasing power.

    Social support: Perceived ability to count on others.
    
    Healthy life expectancy: Average years of healthy life at birth.
    
    Perceptions of corruption: Level of perceived corruption in government and business.
    
    Positive/Negative affect: Measures of emotional well-being.
    
    Confidence in national government: Trust in public institutions.

Statistical Methodology

  1. Base Model & Multicollinearity

     An initial "full" model was constructed using all available predictors.
   
         Performance: Achieved an R^2 of 0.787.
     
         Multicollinearity: Tested using Variance Inflation Factors (VIF); all values remained under 10, suggesting no severe multicollinearity.
     
         Correlations: High correlations were noted between Log GDP per capita and Healthy life expectancy (0.829).
     
  2. Diagnostics & Visualization
  
     Various diagnostic plots were utilized to validate model assumptions:
   
         Residual Analysis: Q-Q plots and Standardized Residual vs. Fitted plots were used to check for normality and homoscedasticity.
     
         Influence: Leverage plots and Cook’s Distance (Residual vs. Leverage) identified influential observations that might skew results.
     
         AV Plots: Added Variable plots helped visualize the marginal contribution of each predictor, hinting at which variables could be removed.
    
  3. Model Selection (The Reduced Model)
   
     To create a more efficient model, several automated and manual steps were taken:
     
         OLS Stepwise Regression: Forward, backward, and "both" AIC-based selection consistently recommended the removal of Negative affect.
     
         The Reduced Model: Retained Log GDP per capita, Social support, Healthy life expectancy, Perceptions of corruption, Positive affect, and Confidence in national government.
     
         Parsimony: While the full model had a slightly higher R^2 (0.787 vs. 0.777), an ANOVA partial F-test suggested the reduced model was superior due to its simplicity and negligible loss in explanatory power.
    
  4. Validation
   
       K-Fold Cross-Validation: A 10-fold CV was performed to assess predictive accuracy.
   
       Error Metrics: The model's Mean Absolute Error (MAE) and Root Mean Square Error (RMSE) were calculated and normalized against the total range of the Life Ladder score to ensure reliability.
   
Key Findings
  
  Predictive Strength: Economic indicators (GDP) and Social Support are highly correlated with happiness, but psychological factors like "Positive Affect" also carry significant weight.
  
  Government Trust: Confidence in national government and perceptions of corruption are statistically significant predictors of a population's "Life Ladder" score.
  
  Model Efficiency: Removing variables like Year and Generosity does not significantly degrade the model's ability to predict happiness.
