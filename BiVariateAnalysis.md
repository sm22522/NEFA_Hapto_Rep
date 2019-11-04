# Bi-Variate NEFA Analysis
---------
## Table of Contents
[Bi-Variate Statistics - Comparing Numeric Variables to BS.NEFA](#bi-variate-statistics---comparing-numerical-variables-to-hapto-log) 

[Bi-Variate Statistics - Comparing Factor Variables to BS.NEFA](#bi-variate-statistics---comparing-factor-variables-to-hapto-log) 

[Bi-Variate Statistics - Comparing Numeric Variables to BS.NEFA.1.2](#bi-variate-statistics---comparing-hapto-035-to-numeric-variables) 

[Bi-Variate Statistics - Comparing Factor Variables to BS.NEFA.1.2](#bi-variate-statistics---comparing-hapto-035-to-factor-variables) 

[Results](#results) 

--------
## Bi-Variate Statistics - Comparing Numeric Variables to BS.NEFA

Now we will test the associations between Hapto.Log and factor variables

For running all our t-tests below:
  H0: beta1 = 0 (no association/no slope between the two variables)
Ha: beta1 notequal 0 (some association/slope between the two variables)
a = 0.05

Our p-value represents the probability of getting a beta1 that matches the one found in our study, purely by chance. 
If this p-value is below 0.05, this is statistically significant and provides convincing evidence against H0.
So we reject H0. There is an association/slope between the two variables
If this p-value is above 0.05, this is not statistically significant and does not provide convincing evidence against H0.
So we fail to reject H0. There is no convincing evidence that there is an association/slope between the two variables.



#### BS.NEFA.Log ~ Hapto.Log - Testing how the cow's haptoglobin levels affected the cow's NEFA levels
```r
#Linear Regression Test
Hapto_Hapto.Log <- lm(BS.NEFA.Log ~ Hapto.Log, hp2)
summary(Hapto_Hapto.Log)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -1.68428    0.09087 -18.535  < 2e-16 ***
#  Hapto.Log    0.07870    0.01166   6.751 3.06e-11 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.7896 on 710 degrees of freedom
#Multiple R-squared:  0.06032,	Adjusted R-squared:  0.05899 
#F-statistic: 45.57 on 1 and 710 DF,  p-value: 3.058e-11
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  

  #### BS.NEFA.Log ~ BS.BHBA.Log - Testing how the cow's blood BHBA levels affected the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_BS.BHBA.Log <- lm(BS.NEFA.Log ~ BS.BHBA.Log, hp2)
summary(Hapto_BS.BHBA.Log)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -0.99899    0.03233 -30.903  < 2e-16 ***
#  BS.BHBA.Log  0.46607    0.06027   7.733 3.62e-14 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.7823 on 710 degrees of freedom
#Multiple R-squared:  0.07767,	Adjusted R-squared:  0.07637 
#F-statistic: 59.79 on 1 and 710 DF,  p-value: 3.616e-14
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ BS.DIM - Testing how the DIM affected the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_BS.DIM <- lm(BS.NEFA.Log ~ BS.DIM, hp2)
summary(Hapto_BS.DIM)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -0.385537   0.095233  -4.048 5.73e-05 ***
#  BS.DIM      -0.036808   0.004641  -7.931 8.46e-15 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.7807 on 710 degrees of freedom
#Multiple R-squared:  0.08138,	Adjusted R-squared:  0.08009 
#F-statistic:  62.9 on 1 and 710 DF,  p-value: 8.464e-15
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ BS.MS.Date.Difference - Testing how the difference in testing days affected the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_BS.MS.Date.Difference <- lm(BS.NEFA.Log ~ BS.MS.Date.Difference, hp2)
summary(Hapto_BS.MS.Date.Difference)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)           -1.02468    0.04152 -24.681  < 2e-16 ***
#  BS.MS.Date.Difference -0.14348    0.05104  -2.811  0.00508 ** 
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.8101 on 710 degrees of freedom
#Multiple R-squared:  0.01101,	Adjusted R-squared:  0.009613 
#F-statistic: 7.901 on 1 and 710 DF,  p-value: 0.005076
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ Calving.No - Testing how the number of calves affected the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_Calving.No <- lm(BS.NEFA.Log ~ Calving.No, hp2)
summary(Hapto_Calving.No)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -1.122373   0.055626 -20.177   <2e-16 ***
#  Calving.No   0.005943   0.015279   0.389    0.697    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.8145 on 710 degrees of freedom
#Multiple R-squared:  0.0002131,	Adjusted R-squared:  -0.001195 
#F-statistic: 0.1513 on 1 and 710 DF,  p-value: 0.6974
```
We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ Milk.Yield - Testing how the milk yield affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_Milk.Yield <- lm(BS.NEFA.Log ~ Milk.Yield, hp2)
summary(Hapto_Milk.Yield)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -1.366903   0.167227  -8.174 4.36e-15 ***
#  Milk.Yield   0.013606   0.005055   2.691  0.00742 ** 
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.7579 on 385 degrees of freedom
#(325 observations deleted due to missingness)
#Multiple R-squared:  0.01847,	Adjusted R-squared:  0.01592 
#F-statistic: 7.244 on 1 and 385 DF,  p-value: 0.007424
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.Milk.Yield - Testing how the amount of milk in the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.Milk.Yield <- lm(BS.NEFA.Log ~ MS.Milk.Yield, hp2)
summary(Hapto_MS.Milk.Yield)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   -1.178044   0.081322 -14.486   <2e-16 ***
#  MS.Milk.Yield  0.004945   0.005054   0.978    0.328    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.814 on 710 degrees of freedom
#Multiple R-squared:  0.001347,	Adjusted R-squared:  -5.993e-05 
#F-statistic: 0.9574 on 1 and 710 DF,  p-value: 0.3282
```
We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.NEFA - Testing how the NEFA level in the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.NEFA <- lm(BS.NEFA.Log ~ MS.NEFA, hp2)
summary(Hapto_MS.NEFA)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -1.29222    0.06944 -18.608  < 2e-16 ***
#  MS.NEFA      0.04963    0.01236   4.017 6.74e-05 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.8081 on 537 degrees of freedom
#(173 observations deleted due to missingness)
#Multiple R-squared:  0.02917,	Adjusted R-squared:  0.02736 
#F-statistic: 16.13 on 1 and 537 DF,  p-value: 6.74e-05
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.BHBA.Log - Testing how the BHBA level in the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.BHBA.Log <- lm(BS.NEFA.Log ~ MS.BHBA.Log, hp2)
summary(Hapto_MS.BHBA.Log)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -2.87951    0.15758  -18.27   <2e-16 ***
#  MS.BHBA.Log  0.46072    0.03799   12.13   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.6973 on 600 degrees of freedom
#(110 observations deleted due to missingness)
#Multiple R-squared:  0.1969,	Adjusted R-squared:  0.1956 
#F-statistic: 147.1 on 1 and 600 DF,  p-value: < 2.2e-16
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.DIM - Testing how the DIM from the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.DIM <- lm(BS.NEFA.Log ~ MS.DIM, hp2)
summary(Hapto_MS.DIM)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -0.424661   0.093377  -4.548 6.37e-06 ***
#  MS.DIM      -0.035823   0.004673  -7.666 5.83e-14 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.7828 on 710 degrees of freedom
#Multiple R-squared:  0.07645,	Adjusted R-squared:  0.07515 
#F-statistic: 58.77 on 1 and 710 DF,  p-value: 5.827e-14
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
 
  
  #### BS.NEFA.Log ~ MS.Fat - Testing how the fat level from the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.Fat <- lm(BS.NEFA.Log ~ MS.Fat, hp2)
summary(Hapto_MS.Fat)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -1.96789    0.12428 -15.835  < 2e-16 ***
#  MS.Fat       0.19234    0.02689   7.153 2.11e-12 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.7867 on 710 degrees of freedom
#Multiple R-squared:  0.06723,	Adjusted R-squared:  0.06591 
#F-statistic: 51.17 on 1 and 710 DF,  p-value: 2.112e-12
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.Protein - Testing how the protein level from the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.Protein <- lm(BS.NEFA.Log ~ MS.Protein, hp2)
summary(Hapto_MS.Protein)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  0.99379    0.30814   3.225  0.00132 ** 
#  MS.Protein  -0.63896    0.09341  -6.840  1.7e-11 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.789 on 710 degrees of freedom
#Multiple R-squared:  0.06183,	Adjusted R-squared:  0.06051 
#F-statistic: 46.79 on 1 and 710 DF,  p-value: 1.705e-11
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.Lactose - Testing how the lactose level from the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.Lactose <- lm(BS.NEFA.Log ~ MS.Lactose, hp2)
summary(Hapto_MS.Lactose)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)
#(Intercept)  -0.4155     0.7664  -0.542    0.588
#MS.Lactose   -0.1427     0.1586  -0.899    0.369

#Residual standard error: 0.8141 on 710 degrees of freedom
#Multiple R-squared:  0.001138,	Adjusted R-squared:  -0.0002687 
#F-statistic: 0.809 on 1 and 710 DF,  p-value: 0.3687
```
We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.Acetone.Log - Testing how the acetone level from the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.Acetone.Log <- lm(BS.NEFA.Log ~ MS.Acetone.Log, hp2)
summary(Hapto_MS.Acetone.Log)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)    -2.71046    0.13830  -19.60   <2e-16 ***
#  MS.Acetone.Log  0.40199    0.03027   13.28   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.6508 on 519 degrees of freedom
#(191 observations deleted due to missingness)
#Multiple R-squared:  0.2537,	Adjusted R-squared:  0.2522 
#F-statistic: 176.4 on 1 and 519 DF,  p-value: < 2.2e-16
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
 
  
  #### BS.NEFA.Log ~ MS.Urea - Testing how the urea level from the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.Urea <- lm(BS.NEFA.Log ~ MS.Urea, hp2)
summary(Hapto_MS.Urea)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -1.177723   0.102585  -11.48   <2e-16 ***
#  MS.Urea      0.002943   0.003926    0.75    0.454    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.8143 on 710 degrees of freedom
#Multiple R-squared:  0.0007912,	Adjusted R-squared:  -0.0006161 
#F-statistic: 0.5622 on 1 and 710 DF,  p-value: 0.4536
```
We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.S.Cell.Count.Log - Testing how the SCC from the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.S.Cell.Count.Log <- lm(BS.NEFA.Log ~ MS.S.Cell.Count.Log, hp2)
summary(Hapto_MS.S.Cell.Count.Log)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)         -1.142054   0.102658 -11.125   <2e-16 ***
#  MS.S.Cell.Count.Log  0.009034   0.023444   0.385      0.7    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.8145 on 710 degrees of freedom
#Multiple R-squared:  0.0002091,	Adjusted R-squared:  -0.001199 
#F-statistic: 0.1485 on 1 and 710 DF,  p-value: 0.7001
```
We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.pH - Testing how the pH of the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.pH <- lm(BS.NEFA.Log ~ MS.pH, hp2)
summary(Hapto_MS.pH)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   9.9951     2.3763   4.206 2.93e-05 ***
#  MS.pH        -1.6726     0.3581  -4.671 3.58e-06 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.8023 on 710 degrees of freedom
#Multiple R-squared:  0.02982,	Adjusted R-squared:  0.02845 
#F-statistic: 21.82 on 1 and 710 DF,  p-value: 3.58e-06
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.SFA - Testing how the Short Fatty Acid content of the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.SFA <- lm(BS.NEFA.Log ~ MS.SFA, hp2)
summary(Hapto_MS.SFA)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -1.37685    0.16419  -8.386 7.71e-16 ***
#  MS.SFA       0.17933    0.06078   2.951  0.00335 ** 
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.7639 on 420 degrees of freedom
#(290 observations deleted due to missingness)
#Multiple R-squared:  0.02031,	Adjusted R-squared:  0.01798 
#F-statistic: 8.706 on 1 and 420 DF,  p-value: 0.003348
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.PFA - Testing how the Poly-Saturated Fatty Acid content of the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.PFA <- lm(BS.NEFA.Log ~ MS.PFA, hp2)
summary(Hapto_MS.PFA)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  -2.1002     0.1204  -17.44   <2e-16 ***
#  MS.PFA        7.5757     0.7329   10.34   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.6891 on 420 degrees of freedom
#(290 observations deleted due to missingness)
#Multiple R-squared:  0.2028,	Adjusted R-squared:  0.2009 
#F-statistic: 106.8 on 1 and 420 DF,  p-value: < 2.2e-16
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.MFA - Testing how the Mono-Saturated Fatty Acid content of the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.MFA <- lm(BS.NEFA.Log ~ MS.MFA, hp2)
summary(Hapto_MS.MFA)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -2.04097    0.08765  -23.29   <2e-16 ***
#  MS.MFA       0.82723    0.05967   13.86   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.6393 on 420 degrees of freedom
#(290 observations deleted due to missingness)
#Multiple R-squared:  0.3139,	Adjusted R-squared:  0.3123 
#F-statistic: 192.2 on 1 and 420 DF,  p-value: < 2.2e-16
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.NSFA - Testing how the Non-Saturated Fatty Acid content of the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.NSFA <- lm(BS.NEFA.Log ~ MS.NSFA, hp2)
summary(Hapto_MS.NSFA)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -2.23991    0.07897  -28.36   <2e-16 ***
#  MS.NSFA      0.06945    0.00455   15.27   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.7068 on 710 degrees of freedom
#Multiple R-squared:  0.2471,	Adjusted R-squared:  0.246 
#F-statistic:   233 on 1 and 710 DF,  p-value: < 2.2e-16
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.Palmeic - Testing how the Palmeic Fatty Acid content of the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.Palmeic <- lm(BS.NEFA.Log ~ MS.Palmeic, hp2)
summary(Hapto_MS.Palmeic)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  -0.5965     0.1794  -3.325 0.000962 ***
#  MS.Palmeic   -0.2764     0.1572  -1.758 0.079499 .  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.769 on 420 degrees of freedom
#(290 observations deleted due to missingness)
#Multiple R-squared:  0.007304,	Adjusted R-squared:  0.00494 
#F-statistic:  3.09 on 1 and 420 DF,  p-value: 0.0795
```
We find that, at a significance level of 0.05, this association is: Barely Not Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.Stearine - Testing how the Stearic Fatty Acid content of the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.Stearine <- lm(BS.NEFA.Log ~ MS.Stearine, hp2)
summary(Hapto_MS.Stearine)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  -2.1529     0.1036  -20.78   <2e-16 ***
#  MS.Stearine   2.4010     0.1896   12.66   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.6566 on 420 degrees of freedom
#(290 observations deleted due to missingness)
#Multiple R-squared:  0.2762,	Adjusted R-squared:  0.2745 
#F-statistic: 160.3 on 1 and 420 DF,  p-value: < 2.2e-16
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ MS.Oleic - Testing how the Oleic Fatty Acid content of the milk sample affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_MS.Oleic <- lm(BS.NEFA.Log ~ MS.Oleic, hp2)
summary(Hapto_MS.Oleic)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept) -1.95076    0.08143  -23.96   <2e-16 ***
#  MS.Oleic     0.82145    0.05912   13.90   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.6388 on 420 degrees of freedom
#(290 observations deleted due to missingness)
#Multiple R-squared:  0.3149,	Adjusted R-squared:  0.3133 
#F-statistic: 193.1 on 1 and 420 DF,  p-value: < 2.2e-16
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ CE.Fat.Level - Testing how the fat level of the back of the cow affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_CE.Fat.Level <- lm(BS.NEFA.Log ~ CE.Fat.Level, hp2)
summary(Hapto_CE.Fat.Level)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  -1.773201   0.075008  -23.64   <2e-16 ***
#  CE.Fat.Level  0.040660   0.004179    9.73   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.7644 on 693 degrees of freedom
#(17 observations deleted due to missingness)
#Multiple R-squared:  0.1202,	Adjusted R-squared:  0.1189 
#F-statistic: 94.67 on 1 and 693 DF,  p-value: < 2.2e-16
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ CE.Temp - Testing how the inner body temperature of the cow affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_CE.Temp <- lm(BS.NEFA.Log ~ CE.Temp, hp2)
summary(Hapto_CE.Temp)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)  
#(Intercept) -1.162583   0.687023  -1.692   0.0911 .
#CE.Temp      0.001512   0.017782   0.085   0.9323  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.8132 on 696 degrees of freedom
#(14 observations deleted due to missingness)
#Multiple R-squared:  1.039e-05,	Adjusted R-squared:  -0.001426 
#F-statistic: 0.00723 on 1 and 696 DF,  p-value: 0.9323
```
We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">
  
  
  #### BS.NEFA.Log ~ CE.Environ.Temp - Testing how the environmental temperature affects the cow's NEFA levels
  ```r
#Linear Regression Test
Hapto_CE.Environ.Temp <- lm(BS.NEFA.Log ~ CE.Environ.Temp, hp2)
summary(Hapto_CE.Environ.Temp)

#Coefficients:
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)     -1.479195   0.086581  -17.08  < 2e-16 ***
#  CE.Environ.Temp  0.022174   0.004863    4.56 6.09e-06 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 0.8029 on 671 degrees of freedom
#(39 observations deleted due to missingness)
#Multiple R-squared:  0.03005,	Adjusted R-squared:  0.02861 
#F-statistic: 20.79 on 1 and 671 DF,  p-value: 6.088e-06
```
We find that, at a significance level of 0.05, this association is: Statistically Significant

Scatterplot:
  <img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">



--------
## Bi-Variate Statistics - Comparing Factor Variables to BS.NEFA




--------
## Bi-Variate Statistics - Comparing Numeric Variables to BS.NEFA.1.2




--------
## Bi-Variate Statistics - Comparing Factor Variables to BS.NEFA.1.2




--------
## Results



