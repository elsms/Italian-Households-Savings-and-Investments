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
A linear regression model is developed to estimate variation in the dependent variable, *savings*, based on demographic and economic predictors. The explanatory variables considered include: 
* *geographical area*
* *number of children*
* *household size*
* *sex*
* *educational attainment*
* *marital status*
* *age*
* *financial assets*
* *net income*
* *consumption*

Given the strong positive correlation between *savings* and *net income*, a logarithmic transformation is applied to both variables to mitigate skewness and stabilize variance. The resulting improvement in the model’s R<sup>2</sup> indicates that the transformed specification better captures variability in the output.

Finally, to address potential heteroskedasticity, where the variance of the error term may depend on the regressors, robust standard errors are estimated, improving the reliability of statistical inference.

### Logistic Regression 
The second model, the logistic regression one, is computed to investigate the likelihood of households investing in the financial assets considered. The explained variable used is given by the ratio of savings to net income to determine the probability that households would invest in the assets considered if the ratio exceeded an arbitrary threshold of 0.2. If the ratio was below the threshold, the household was considered not to invest. In performing the logistic regression, the robust option was again used to address potential heteroskedasticity. 

# Key findings 
### Linear Regression 
| Variable | Summary of Findings |
|----------|--------------------|
| Geographical Area | Statistically significant only for individuals from the South, possibly reflecting regional economic disparities. |
| Number of Children | Negative and statistically significant; households with children tend to have higher expenses, reducing savings. |
| Household Size | Negative and statistically significant; larger households have higher consumption needs, limiting the portion of income that can be saved. |
| Educational Attainment | Negative and statistically significant for high school, bachelor’s, master’s, and PhD levels; higher education may be associated with increased consumption due to higher income and lifestyle expectations. |
| Marital Status | Positive and statistically significant; single individuals may have fewer shared financial obligations compared to married households. |
| Age | Negative and statistically significant for those aged 35-44; life-cycle financial responsibilities such as housing or childcare may temporarily reduce savings. |
| Financial Assets | Positive and statistically significant; individuals with higher asset holdings tend to save more, supporting wealth accumulation. |
| Consumption | Negative and statistically significant; reflects the trade-off between consumption and savings. |

### Logistic Regression 
| Variable | Summary of Findings |
|----------|--------------------|
| Geographical Area | Households from the South and Center are more likely to invest compared to those from Northern Italy (reference group). |
| Household Size | Statistically significant and negative; larger households are less likely to invest, possibly due to higher expenses. |
| Educational Attainment | Results suggest that individuals with lower education levels are more likely to invest compared to those with higher education. |
| Consumption | Highly statistically significant and negative; higher consumption reduces the likelihood of investing. |
| Net Income | Positive and statistically significant; higher net income increases the probability of investing. |

Running separate logistic regressions for each risky assets:
* Men are more likely than women to invest in risky assets, indicating greater risk tolerance.
* Higher education is associated with greater financial literacy and a higher propensity to take financial risks.
* Younger and older individuals are less likely to invest in risky assets, consistent with the Life-Cycle Theory, which suggests risk-taking peaks around mid-life.
  
# Conclusion 
In conclusion, the analysis highlights that *geographical area*, *household size*, *educational
attainment*, *age*, and *marital status* significantly influence savings and investment behaviors. Households from the North and Center are more likely to invest in risky assets compared to those in the South. Larger households and those with children tend to save less and invest less. Higher levels of education increase the likelihood of investing in risky assets, while higher consumption and lower income decrease the probability of investing. Finally, men are more likely to invest in risky assets than women.
