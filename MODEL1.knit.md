---
title: "MODEL"
author: "Wallstreet Petrus-Nihi"
editor: visual
execute:
  echo: false
  warning: false
  message: false
---


### **Research Question**: How does the risk of heart disease vary across different age groups and between genders?




::: {.cell}
::: {.cell-output .cell-output-stdout}

```
spc_tbl_ [308,854 × 19] (S3: spec_tbl_df/tbl_df/tbl/data.frame)
 $ General_Health              : chr [1:308854] "Poor" "Very Good" "Very Good" "Poor" ...
 $ Checkup                     : chr [1:308854] "Within the past 2 years" "Within the past year" "Within the past year" "Within the past year" ...
 $ Exercise                    : chr [1:308854] "No" "No" "Yes" "Yes" ...
 $ Heart_Disease               : chr [1:308854] "No" "Yes" "No" "Yes" ...
 $ Skin_Cancer                 : chr [1:308854] "No" "No" "No" "No" ...
 $ Other_Cancer                : chr [1:308854] "No" "No" "No" "No" ...
 $ Depression                  : chr [1:308854] "No" "No" "No" "No" ...
 $ Diabetes                    : chr [1:308854] "No" "Yes" "Yes" "Yes" ...
 $ Arthritis                   : chr [1:308854] "Yes" "No" "No" "No" ...
 $ Sex                         : chr [1:308854] "Female" "Female" "Female" "Male" ...
 $ Age_Category                : chr [1:308854] "70-74" "70-74" "60-64" "75-79" ...
 $ Height_(cm)                 : num [1:308854] 150 165 163 180 191 183 175 165 163 163 ...
 $ Weight_(kg)                 : num [1:308854] 32.7 77.1 88.5 93.4 88.5 ...
 $ BMI                         : num [1:308854] 14.5 28.3 33.5 28.7 24.4 ...
 $ Smoking_History             : chr [1:308854] "Yes" "No" "No" "No" ...
 $ Alcohol_Consumption         : num [1:308854] 0 0 4 0 0 0 0 3 0 0 ...
 $ Fruit_Consumption           : num [1:308854] 30 30 12 30 8 12 16 30 12 12 ...
 $ Green_Vegetables_Consumption: num [1:308854] 16 0 3 30 4 12 8 8 12 12 ...
 $ FriedPotato_Consumption     : num [1:308854] 12 4 16 8 0 12 0 8 4 1 ...
 - attr(*, "spec")=
  .. cols(
  ..   General_Health = col_character(),
  ..   Checkup = col_character(),
  ..   Exercise = col_character(),
  ..   Heart_Disease = col_character(),
  ..   Skin_Cancer = col_character(),
  ..   Other_Cancer = col_character(),
  ..   Depression = col_character(),
  ..   Diabetes = col_character(),
  ..   Arthritis = col_character(),
  ..   Sex = col_character(),
  ..   Age_Category = col_character(),
  ..   `Height_(cm)` = col_double(),
  ..   `Weight_(kg)` = col_double(),
  ..   BMI = col_double(),
  ..   Smoking_History = col_character(),
  ..   Alcohol_Consumption = col_double(),
  ..   Fruit_Consumption = col_double(),
  ..   Green_Vegetables_Consumption = col_double(),
  ..   FriedPotato_Consumption = col_double()
  .. )
 - attr(*, "problems")=<externalptr> 
```


:::

::: {.cell-output .cell-output-stdout}

```

    No    Yes 
283883  24971 
```


:::

::: {.cell-output .cell-output-stdout}

```
# A tibble: 6 × 19
  General_Health Checkup         Exercise Heart_Disease Skin_Cancer Other_Cancer
  <chr>          <chr>           <chr>            <dbl> <chr>       <chr>       
1 Poor           Within the pas… No                   0 No          No          
2 Very Good      Within the pas… No                   1 No          No          
3 Very Good      Within the pas… Yes                  0 No          No          
4 Poor           Within the pas… Yes                  1 No          No          
5 Good           Within the pas… No                   0 No          No          
6 Good           Within the pas… No                   0 No          No          
# ℹ 13 more variables: Depression <chr>, Diabetes <chr>, Arthritis <chr>,
#   Sex <chr>, Age_Category <chr>, `Height_(cm)` <dbl>, `Weight_(kg)` <dbl>,
#   BMI <dbl>, Smoking_History <chr>, Alcohol_Consumption <dbl>,
#   Fruit_Consumption <dbl>, Green_Vegetables_Consumption <dbl>,
#   FriedPotato_Consumption <dbl>
```


:::
:::

::: {.cell}
::: {.cell-output .cell-output-stdout}

```

Call:
glm(formula = Heart_Disease ~ Age_Category + Sex + BMI + Smoking_History + 
    Exercise, family = binomial, data = heart)

Coefficients:
                    Estimate Std. Error z value Pr(>|z|)    
(Intercept)        -6.263137   0.109289 -57.308  < 2e-16 ***
Age_Category25-29   0.234938   0.140116   1.677   0.0936 .  
Age_Category30-34   0.581930   0.125538   4.635 3.56e-06 ***
Age_Category35-39   0.747269   0.120161   6.219 5.01e-10 ***
Age_Category40-44   1.143116   0.114429   9.990  < 2e-16 ***
Age_Category45-49   1.632562   0.110760  14.740  < 2e-16 ***
Age_Category50-54   2.030260   0.107820  18.830  < 2e-16 ***
Age_Category55-59   2.461612   0.106180  23.183  < 2e-16 ***
Age_Category60-64   2.746586   0.105351  26.071  < 2e-16 ***
Age_Category65-69   3.000166   0.104994  28.575  < 2e-16 ***
Age_Category70-74   3.299891   0.104815  31.483  < 2e-16 ***
Age_Category75-79   3.560462   0.105179  33.852  < 2e-16 ***
Age_Category80+     3.871642   0.104880  36.915  < 2e-16 ***
SexMale             0.659632   0.014198  46.460  < 2e-16 ***
BMI                 0.030743   0.001076  28.579  < 2e-16 ***
Smoking_HistoryYes  0.548212   0.014058  38.997  < 2e-16 ***
ExerciseYes        -0.449982   0.015039 -29.922  < 2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

(Dispersion parameter for binomial family taken to be 1)

    Null deviance: 173478  on 308853  degrees of freedom
Residual deviance: 148281  on 308837  degrees of freedom
AIC: 148315

Number of Fisher Scoring iterations: 7
```


:::
:::


## **Context**

Heart disease remains the leading cause of death globally, with age and gender being two of the most significant factors influencing its development. The likelihood of heart disease increases with age, and there are notable differences in risk between males and females. Understanding how these factors interplay is crucial for both unraveling the complexities of heart disease and enhancing preventive measures. By utilizing data modeling techniques, we can visualize and analyze how variations in age and gender contribute to heart disease risk. This approach helps reveal underlying patterns and relationships, supporting the development of more effective prevention strategies and informing public health initiatives aimed at reducing heart disease incidence.

Age + Gender vs Heart Disease

To assess which factor—age or gender—has a greater impact on the risk of heart disease, a Logisitic Regression model can be constructed. This model will enable an analysis of how each factor influences the likelihood of developing heart disease, offering insights into their relative contributions and helping to identify the most significant predictors.

### 1. Logistic Regression Model

The logistic regression model is given by:

$$ \log \left( \frac{1 - p}{p} \right) = \beta_0 + \beta_1 \cdot \text{Age Category} + \beta_2 \cdot \text{Gender} + \epsilon $$

### 2. Table

```         
### **Interpreting the Coefficient Table**

| Characteristic    | Beta  | 95% CI       |
|-------------------|-------|--------------|
| **Intercept**     | -5.72 | -5.93, -5.52 |
| **Gender (Male)** | 0.68  | 0.65, 0.71   |
| **Age 25-29**     | 0.39  | 0.11, 0.66   |
| **Age 30-34**     | 0.81  | 0.56, 1.06   |
| **Age 35-39**     | 1.02  | 0.79, 1.26   |
| **Age 40-44**     | 1.46  | 1.23, 1.68   |
| **Age 45-49**     | 1.95  | 1.73, 2.16   |
| **Age 50-54**     | 2.33  | 2.12, 2.54   |
| **Age 55-59**     | 2.78  | 2.57, 2.98   |
| **Age 60-64**     | 3.07  | 2.87, 3.28   |
| **Age 65-69**     | 3.31  | 3.10, 3.51   |
| **Age 70-74**     | 3.61  | 3.40, 3.81   |
| **Age 75-79**     | 3.87  | 3.67, 4.08   |
| **Age 80+**       | 4.14  | 3.93, 4.34   |

**CI** = Confidence Interval
```

### 3. Model of Posterior Prediction (Age + Gender)


::: {.cell}
::: {.cell-output-display}
![](MODEL1_files/figure-html/unnamed-chunk-3-1.png){width=672}
:::
:::


### Implications of the Graph on Heart Disease Risk:

1.  **Age as a Risk Factor**:
    -   The graph likely shows a **positive relationship between age and the predicted probability of heart disease**. This means that as individuals get older, their likelihood of developing heart disease increases. This is important for public health awareness: older adults should be particularly vigilant about heart disease risk factors (e.g., cholesterol levels, blood pressure, lifestyle choices).
2.  **Gender Differences in Risk**:
    -   If the graph indicates differing probabilities of heart disease between males and females in the same age categories, it suggests that **gender plays a significant role in heart disease risk**. For instance:
        -   If males show higher predicted probabilities than females at certain ages, it indicates that men might need to engage more urgently in preventive measures (e.g., regular medical check-ups, lifestyle changes).
        -   Conversely, if women’s predicted probabilities rise sharply post-menopause, it emphasizes the need for increased awareness and prevention strategies for older women.
3.  **Targeted Prevention Strategies**:
    -   The information from the graph can inform **targeted interventions and healthcare planning**. For example:
        -   **Older age categories** might benefit from heart health screenings, education about symptoms of heart disease, and lifestyle modification programs aimed specifically at older adults.
        -   Public health campaigns could focus on raising awareness about heart disease risk among men in their 40s to 60s if those groups show higher probabilities.
4.  **Understanding Risk Management**:
    -   Those individuals and healthcare providers can use insights from the graph to **prioritize interventions** based on age and gender.
    -   Individuals who fall into higher-risk groups (e.g., older adults or males based on the trends observed) can be encouraged to **adopt heart-healthy behaviors**—such as maintaining a balanced diet, exercising regularly, managing stress, and monitoring their heart health closely.
5.  **Implications for Screening and Early Detection**:
    -   The visual data can promote a **greater emphasis on regular screenings** for heart disease in high-risk categories as indicated by the graph. Understanding that certain age groups have higher risks can motivate users to seek preventive care proactively.
6.  **Societal Impact**:
    -   Beyond individual implications, the data can inform public health policies and funding allocation towards **heart disease research, education, and resources**, particularly aimed at groups identified as having a higher predicted probability of developing heart disease.

### Conclusion:

The graph ultimately serves as a critical tool in understanding how age and gender impact heart disease risk among individuals. By illustrating these predicted probabilities, it emphasizes the need for personalized risk assessment, prevention strategies, and early intervention to improve cardiovascular health outcomes across different segments of the population. Individuals, healthcare providers, and policymakers can all use this information to increase awareness and take proactive steps in managing heart disease risk.

