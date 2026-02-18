l.
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
* **linear regression**
* **logistic regression**

### Linear Regression 
A linear regression model is developed to estimate variation in the dependent variable, *savings*, based on demographic and economic predictors. The explanatory variables considered include *geographical area*, *number of children*, *household size*, *sex*, *educational attainment*, *marital status*, *age*, *financial assets*, *net income*, and *consumption*.

Given the strong positive correlation between *savings* and *net income*, a logarithmic transformation is applied to both variables to mitigate skewness and stabilize variance. The resulting improvement in the model’s R<sup>2</sup> indicates that the transformed specification better captures variability in the output.

Finally, to address potential heteroskedasticity, where the variance of the error term may depend on the regressors, robust standard errors are estimated, improving the reliability of statistical inference.

### Logistic Regression 
The second model, the logistic regression one, is computed to investigate the likelihood of households investing in the financial assets considered. The explained variable used is given by the ratio of savings to net income to determine the probability that households would invest in the assets considered if the ratio exceeded an arbitrary threshold of 0.2. If the ratio was below the threshold, the household was considered not to invest. In performing the logistic regression, the robust option was again used to address potential heteroskedasticity. 

# Key findings 
### Linear Regression 
* *Geographical area* is statistically significant only for individuals from the South, which may reflect regional economic disparities.
* The presence of *children* negatively impacts savings, as households with children tend to have higher expenses.
* Larger *household size* is statistically significant and associated with lower savings. Bigger households generally have higher consumption needs, limiting the portion of income that can be set aside.
* *Education attainment* shows negative and statistically significant coefficients for individuals with a high school diploma, bachelor’s degree, master’s degree, and PhD. This could be explained by the idea that individuals with higher education may prioritize current consumption over savings, possibly due to higher income leading to a higher standard of living and more consumption.
* *Marital status* is statistically significant, with single individuals showing a positive coefficient. This may reflect fewer shared financial obligations compared to married households, where income is often directed toward joint or family expenses.
* Only the 35–44 *age* group is statistically significant. The negative coefficient is consistent with life-cycle consumption patterns, where financial responsibilities such as housing or childcare may temporarily reduce savings.
* *Financial assets* are positively and statistically significant, indicating that individuals with higher asset holdings tend to save more. Greater available resources support continued saving and wealth accumulation.
* *Consumption* is statistically significant and has a negative sign, suggesting the expected trade-off: as savings increase, consumption decreases, and vice versa. 

### Logistic Regression 



# Conclusion 
