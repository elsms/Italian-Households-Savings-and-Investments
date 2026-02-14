
[![Stata](https://img.shields.io/badge/Stata-Do%20File-blue)](Project.do)

# Introduction 
This project, completed for the [Economics of Risk and Agent Behavior](https://www.unive.it/data/course/506445) module at [Ca' Foscari University of Venice](https://www.unive.it/web/en/497/home), explores how demographic and economic factors influenced Italian households' saving and investment decisions in 2022.

Building on Franco Modigliani’s **Life-Cycle Hypothesis**, which suggests individuals smooth consumption over their lifetime, the analysis uses empirical data to show that households do not invest optimally. In practice, the model does not fully hold. Several factors may explain this general lack of participation in financial markets, ranging from asymmetric information and insufficient financial literacy to risk aversion. Additionally, factors such as age, gender, and seasonality have been shown to affect risk aversion and, consequently, investment decisions. This analysis demonstrates how age, income, and household composition strongly influence saving and investment behavior.

The findings highlight that real-world financial decisions are shaped by multiple factors beyond the simple lifetime optimization proposed by the model.

# Data 
The analysis uses the [**2022 Survey on Household Income and Wealth (SHIW)**](https://www.bancaditalia.it/statistiche/tematiche/indagini-famiglie-imprese/bilanci-famiglie/index.html?com.dotmarketing.htmlpage.language=1&dotcache=refresh) conducted by the Bank of Italy.

The dataset provides detailed information on Italian households' income and savings in the year 2022. The analysis focuses on: 
* household structure and household members' characteristics
* work and income
* saving and investment decisions

The data used is available in this [folder](Data). 

# Methodology 
Two models are developed using the following strategies: 
* Linear regression
* Logistic regression

### Linear Regression 
A linear regression model is developed to estimate variation in the dependent variable, *savings*, based on demographic and economic predictors. The explanatory variables considered include *geographical area*, *number of children*, *household size*, *sex*, *educational attainment*, *marital status*, *age*, *financial assets*, *net income*, and *consumption*.

Given the strong positive correlation between *savings* and *net income*, a logarithmic transformation is applied to both variables to mitigate skewness and stabilize variance. The resulting improvement in the model’s R<sup>2</sup> indicates that the transformed specification better captures variability in the output.

Finally, to address potential heteroskedasticity, where the variance of the error term may depend on the regressors, robust standard errors are estimated, improving the reliability of statistical inference.


# Key findings 

# Conclusion 
