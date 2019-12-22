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
  <img src="https://user-images.githubusercontent.com/52465712/68156858-2e223a00-ff12-11e9-89a2-cf1c4469b801.png" width="300">
  

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
  <img src="https://user-images.githubusercontent.com/52465712/68156859-2e223a00-ff12-11e9-8697-415baa10845c.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156861-2e223a00-ff12-11e9-9cf6-dcaccad948d2.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156862-2e223a00-ff12-11e9-9aeb-0bb851466817.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156863-2e223a00-ff12-11e9-872f-a0b46361e1e4.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156864-2e223a00-ff12-11e9-8116-e616b10c7c36.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156845-2d89a380-ff12-11e9-8925-871e3cdd42da.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156846-2d89a380-ff12-11e9-9565-a4d6f8975268.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156847-2d89a380-ff12-11e9-96bd-854a87fab4f7.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156849-2d89a380-ff12-11e9-839a-b628cb10514a.png" width="300">
 
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156850-2d89a380-ff12-11e9-90e7-e6b972974a90.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156853-2d89a380-ff12-11e9-9a3f-da204a7b2c17.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156855-2d89a380-ff12-11e9-8b18-9653e71b1e44.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68156856-2e223a00-ff12-11e9-84f6-212aa650fcd2.png" width="300">
 
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157238-e6e87900-ff12-11e9-871d-c6ce88814867.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157233-e64fe280-ff12-11e9-8405-48212ae273ee.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157232-e64fe280-ff12-11e9-9c14-97d880ab49ce.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157234-e6e87900-ff12-11e9-899c-f535c85758de.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157241-e6e87900-ff12-11e9-82de-403dc1d84206.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157738-dedd0900-ff13-11e9-9f4a-7138af7d3163.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157240-e6e87900-ff12-11e9-902d-68899fe2ab3a.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157236-e6e87900-ff12-11e9-8b89-51289b65d706.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157237-e6e87900-ff12-11e9-8d6f-36d8e7415543.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157235-e6e87900-ff12-11e9-976c-b09f808b42d4.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157737-dedd0900-ff13-11e9-9978-052eaa6eb4f0.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157741-df759f80-ff13-11e9-8db4-8ed080f392bd.png" width="300">
  
  
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
  <img src="https://user-images.githubusercontent.com/52465712/68157740-df759f80-ff13-11e9-8b76-2c0e342513fa.png" width="300">



--------
## Bi-Variate Statistics - Comparing Factor Variables to BS.NEFA




--------
## Bi-Variate Statistics - Comparing Numeric Variables to BS.NEFA.1.2

Now we will test the associations between BS.NEFA.0.7 and numerical variables

For running all our t-tests below:
  H0: beta1 = 0 (no association/no slope between the two variables)
Ha: beta1 notequal 0 (some association/slope between the two variables)
a = 0.05

Our p-value represents the probability of getting a beta1 that matches the one found in our study, purely by chance. 
If this p-value is below 0.05, this is statistically significant and provides convincing evidence against H0.
So we reject H0. There is an association/slope between the two variables
If this p-value is above 0.05, this is not statistically significant and does not provide convincing evidence against H0.
So we fail to reject H0. There is no convincing evidence that there is an association/slope between the two variables.



#### BS.NEFA.0.7 ~ Hapto.Log - Testing how the cow's haptoglobin levels affected the cow's NEFA levels with a cutoff value
```r
#Logistic regression test
BS.NEFA.0.7_Hapto.Log <- glm(BS.NEFA.0.7 ~ Hapto.Log, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_Hapto.Log)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -3.14013    0.29216 -10.748  < 2e-16 ***
#  Hapto.Log    0.22254    0.03375   6.594 4.27e-11 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 663.13  on 710  degrees of freedom
#AIC: 667.13

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_Hapto.Log), confint(BS.NEFA.0.7_Hapto.Log)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.04327727 0.02417083 0.07609058
#Hapto.Log   1.24924297 1.16944614 1.33516986

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.1694 & 1.3352
- The Odds Ratio is: 1.2492

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  

  
  
  #### BS.NEFA.0.7 ~ BS.BHBA.Log - Testing how the cow's BHBA levels affected the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_BS.BHBA.Log <- glm(BS.NEFA.0.7 ~ BS.BHBA.Log, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_BS.BHBA.Log)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -1.22241    0.09905 -12.342  < 2e-16 ***
#  BS.BHBA.Log  1.32594    0.19680   6.737 1.61e-11 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 657.13  on 710  degrees of freedom
#AIC: 661.13

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_BS.BHBA.Log), confint(BS.NEFA.0.7_BS.BHBA.Log)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.2945195 0.2418376 0.3566975
#BS.BHBA.Log 3.7657158 2.5764675 5.5824351

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 2.5765 & 5.5824
- The Odds Ratio is: 3.7657

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  

  
  
  #### BS.NEFA.0.7 ~ BS.DIM - Testing how the cow's DIM affected the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_BS.DIM <- glm(BS.NEFA.0.7 ~ BS.DIM, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_BS.DIM)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -0.28746    0.29671  -0.969 0.332644    
#BS.DIM      -0.05952    0.01550  -3.839 0.000123 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 690.59  on 710  degrees of freedom
#AIC: 694.59

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_BS.DIM), confint(BS.NEFA.0.7_BS.DIM)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.7501695 0.4176751 1.3388568
#BS.DIM      0.9422159 0.9136450 0.9709781

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9136 & 0.9710
- The Odds Ratio is: 0.9422

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  

  
  
  #### BS.NEFA.0.7 ~ BS.MS.Date.Difference - Testing how the difference between the sample taken days affected the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_BS.MS.Date.Difference <- glm(BS.NEFA.0.7 ~ BS.MS.Date.Difference, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_BS.MS.Date.Difference)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)            -1.2199     0.1208 -10.102   <2e-16 ***
#  BS.MS.Date.Difference  -0.3637     0.1570  -2.316   0.0206 *  
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 700.52  on 710  degrees of freedom
#AIC: 704.52

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_BS.MS.Date.Difference), confint(BS.NEFA.0.7_BS.MS.Date.Difference)))

#                     OR     2.5 %     97.5 %
#(Intercept)           0.2952668 0.2317166 0.3723023
#BS.MS.Date.Difference 0.6951242 0.5105606 0.9458406

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.5106 & 0.9458
- The Odds Ratio is: 0.6951

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ Calving.No - Testing how the cow's number of calves affected the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_Calving.No <- glm(BS.NEFA.0.7 ~ Calving.No, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_Calving.No)

#Coefficients:
# Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -1.32489    0.17144  -7.728 1.09e-14 ***
#  Calving.No  -0.02744    0.04808  -0.571    0.568    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 705.54  on 710  degrees of freedom
#AIC: 709.54

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_Calving.No), confint(BS.NEFA.0.7_Calving.No)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.2658330 0.1891393 0.3706532
#Calving.No  0.9729317 0.8833916 1.0670633

```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.8834 & 1.0671
- The Odds Ratio is: 0.9729

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ Milk.Yield - Testing how the cow's milk yield affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_Milk.Yield <- glm(BS.NEFA.0.7 ~ Milk.Yield, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_Milk.Yield)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -1.86111    0.52663  -3.534 0.000409 ***
#  Milk.Yield   0.02438    0.01562   1.561 0.118535    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 440.12  on 386  degrees of freedom
#Residual deviance: 437.64  on 385  degrees of freedom
#(325 observations deleted due to missingness)
#AIC: 441.64

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_Milk.Yield), confint(BS.NEFA.0.7_Milk.Yield)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.1554998 0.05385953 0.4267294
#Milk.Yield  1.0246815 0.99410724 1.0570552

```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9941 & 1.0571
- The Odds Ratio is: 1.0247

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.Milk.Yield - Testing how the cow's milk sample yield affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.Milk.Yield <- glm(BS.NEFA.0.7 ~ MS.Milk.Yield, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.Milk.Yield)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   -1.01724    0.26068  -3.902 9.53e-05 ***
#  MS.Milk.Yield -0.02668    0.01694  -1.575    0.115    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 703.24  on 710  degrees of freedom
#AIC: 707.24

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.Milk.Yield), confint(BS.NEFA.0.7_MS.Milk.Yield)))

#                     OR     2.5 %     97.5 %
#(Intercept)   0.3615914 0.2177951 0.6059317
#MS.Milk.Yield 0.9736720 0.9407232 1.0054229

```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9407 & 1.0054
- The Odds Ratio is: 0.9737

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.NEFA - Testing how the cow's NEFA levels in her milk affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.NEFA <- glm(BS.NEFA.0.7 ~ MS.NEFA, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.NEFA)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -1.84421    0.22733  -8.113 4.96e-16 ***
#  MS.NEFA      0.11604    0.03761   3.085  0.00203 ** 
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 571.58  on 538  degrees of freedom
#Residual deviance: 561.83  on 537  degrees of freedom
#(173 observations deleted due to missingness)
#AIC: 565.83

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.NEFA), confint(BS.NEFA.0.7_MS.NEFA)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.1581499 0.09978576 0.243690
#MS.NEFA     1.1230428 1.04389616 1.210038

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.0439 & 1.2100
- The Odds Ratio is: 1.1230

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.BHBA.Log - Testing how the cow's BHBA levels in milk affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.BHBA.Log <- glm(BS.NEFA.0.7 ~ MS.BHBA.Log, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.BHBA.Log)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -7.1028     0.7735  -9.183  < 2e-16 ***
#  MS.BHBA.Log   1.3797     0.1741   7.923 2.32e-15 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 645.74  on 601  degrees of freedom
#Residual deviance: 563.99  on 600  degrees of freedom
#(110 observations deleted due to missingness)
#AIC: 567.99

#Number of Fisher Scoring iterations: 5

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.BHBA.Log), confint(BS.NEFA.0.7_MS.BHBA.Log)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.0008228055 0.0001696345 0.003535706
#MS.BHBA.Log 3.9735278634 2.8569759193 5.660908475

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 2.8570 & 5.6609
- The Odds Ratio is: 3.9735

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.DIM - Testing how the cow's DIM affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.DIM <- glm(BS.NEFA.0.7 ~ MS.DIM, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.DIM)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -0.37396    0.28974  -1.291  0.19681    
#MS.DIM      -0.05647    0.01550  -3.642  0.00027 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 692.18  on 710  degrees of freedom
#AIC: 696.18

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.DIM), confint(BS.NEFA.0.7_MS.DIM)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.6880074 0.3881544 1.2106032
#MS.DIM      0.9450991 0.9164581 0.9739724

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9165 & 0.9740
- The Odds Ratio is: 0.9451

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.Fat - Testing how the cow's fat levels affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.Fat <- glm(BS.NEFA.0.7 ~ MS.Fat, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.Fat)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -4.01960    0.43408  -9.260  < 2e-16 ***
#  MS.Fat       0.55946    0.08804   6.355 2.09e-10 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 661.74  on 710  degrees of freedom
#AIC: 665.74

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.Fat), confint(BS.NEFA.0.7_MS.Fat)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.01796011 0.0074756 0.04113887
#MS.Fat      1.74972304 1.4776429 2.08861283

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.4776 & 2.0886
- The Odds Ratio is: 1.7497

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.Protein - Testing how the cow's protein levels affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.Protein <- glm(BS.NEFA.0.7 ~ MS.Protein, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.Protein)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   4.1607     1.1034   3.771 0.000163 ***
# MS.Protein   -1.7209     0.3443  -4.998 5.79e-07 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 678.44  on 710  degrees of freedom
#AIC: 682.44

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.Protein), confint(BS.NEFA.0.7_MS.Protein)))

#                     OR     2.5 %     97.5 %
#(Intercept) 64.1148552 7.58788795 576.5672426
#MS.Protein   0.1789022 0.08986398   0.3470675

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.0899 & 0.3471
- The Odds Ratio is: 0.1789

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.Lactose - Testing how the milk's lactose level affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.Lactose <- glm(BS.NEFA.0.7 ~ MS.Lactose, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.Lactose)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)
#(Intercept)   1.7128     2.2373   0.766    0.444
#MS.Lactose   -0.6473     0.4644  -1.394    0.163

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 703.97  on 710  degrees of freedom
#AIC: 707.97

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.Lactose), confint(BS.NEFA.0.7_MS.Lactose)))

#                     OR     2.5 %     97.5 %
#(Intercept) 5.5445488 0.06233196 452.506626
#MS.Lactose  0.5234596 0.20962842   1.326273

```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.2096 & 1.3263
- The Odds Ratio is: 0.5235

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.Acetone.Log - Testing how the milk's acetone levels affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.Acetone.Log <- glm(BS.NEFA.0.7 ~ MS.Acetone.Log, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.Acetone.Log)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)     -6.3079     0.7047  -8.951  < 2e-16 ***
#  MS.Acetone.Log   1.1210     0.1446   7.751 9.15e-15 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 591.92  on 520  degrees of freedom
#Residual deviance: 511.35  on 519  degrees of freedom
#(191 observations deleted due to missingness)
#AIC: 515.35

#Number of Fisher Scoring iterations: 5

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.Acetone.Log), confint(BS.NEFA.0.7_MS.Acetone.Log)))

#                     OR     2.5 %     97.5 %
#(Intercept)    0.001821786 0.00042993 0.006842758
#MS.Acetone.Log 3.068043345 2.33562693 4.122013015

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 2.3356 & 4.1220
- The Odds Ratio is: 3.0680

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.Urea - Testing how the milk's urea levels affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.Urea <- glm(BS.NEFA.0.7 ~ MS.Urea, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.Urea)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -1.56717    0.31474  -4.979 6.38e-07 ***
#  MS.Urea      0.00637    0.01192   0.534    0.593    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 705.59  on 710  degrees of freedom
#AIC: 709.59

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.Urea), confint(BS.NEFA.0.7_MS.Urea)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.208635 0.1125195 0.3874585
#MS.Urea     1.006390 0.9826336 1.0298071

```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9826 & 1.0298
- The Odds Ratio is: 1.0064

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  
  #### BS.NEFA.0.7 ~ MS.S.Cell.Count.Log - Testing how the milk's SCC  levels affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.S.Cell.Count.Log <- glm(BS.NEFA.0.7 ~ MS.S.Cell.Count.Log, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.S.Cell.Count.Log)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)         -1.60665    0.31665  -5.074  3.9e-07 ***
#  MS.S.Cell.Count.Log  0.04736    0.07147   0.663    0.508    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 705.43  on 710  degrees of freedom
#AIC: 709.43

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.S.Cell.Count.Log), confint(BS.NEFA.0.7_MS.S.Cell.Count.Log)))

#                     OR     2.5 %     97.5 %
#(Intercept)         0.2005576 0.1073794 0.3721972
#MS.S.Cell.Count.Log 1.0484982 0.9096975 1.2044724

```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9097 & 1.2045
- The Odds Ratio is: 1.0485

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.pH - Testing how the milk's pH levels affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.pH <- glm(BS.NEFA.0.7 ~ MS.pH, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.pH)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)  
#(Intercept)   15.869      6.882   2.306   0.0211 *
#  MS.pH         -2.606      1.039  -2.509   0.0121 *
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 699.77  on 710  degrees of freedom
#AIC: 703.77

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.pH), confint(BS.NEFA.0.7_MS.pH)))

#                     OR     2.5 %     97.5 %
#(Intercept) 7.795210e+06 9.309740985 6.017084e+12
#MS.pH       7.386165e-02 0.009539736 5.777644e-01

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.0095 & 0.5778
- The Odds Ratio is: 0.0095

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  
  #### BS.NEFA.0.7 ~ MS.SFA - Testing how the milk's saturated fatty acid levels affect the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.SFA <- glm(BS.NEFA.0.7 ~ MS.SFA, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.SFA)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -2.7704     0.5165  -5.364 8.14e-08 ***
#  MS.SFA        0.6622     0.1850   3.580 0.000344 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 492.39  on 421  degrees of freedom
#Residual deviance: 478.87  on 420  degrees of freedom
#(290 observations deleted due to missingness)
#AIC: 482.87

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.SFA), confint(BS.NEFA.0.7_MS.SFA)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.06263751 0.02206818 0.1681001
#MS.SFA      1.93909771 1.35824293 2.8117401

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.3582 & 2.8117
- The Odds Ratio is: 1.9391

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.PFA - Testing how the milk's polyunsaturated fatty acid levels affect the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.PFA <- glm(BS.NEFA.0.7 ~ MS.PFA, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.PFA)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -4.6440     0.5273  -8.807  < 2e-16 ***
#  MS.PFA       22.0430     3.0159   7.309 2.69e-13 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 492.39  on 421  degrees of freedom
#Residual deviance: 423.24  on 420  degrees of freedom
#(290 observations deleted due to missingness)
#AIC: 427.24

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.PFA), confint(BS.NEFA.0.7_MS.PFA)))

#                     OR     2.5 %     97.5 %
#(Intercept) 9.619258e-03 3.269512e-03 2.593933e-02
#MS.PFA      3.742525e+09 1.264863e+07 1.768876e+12

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.264863e7 & 1.768876e12
- The Odds Ratio is: 3.742525e9

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.MFA - Testing how the milk's monosaturated fatty acid levels affect the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.MFA <- glm(BS.NEFA.0.7 ~ MS.MFA, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.MFA)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -4.3571     0.4355  -10.01   <2e-16 ***
#  MS.MFA        2.3060     0.2792    8.26   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 492.39  on 421  degrees of freedom
#Residual deviance: 395.55  on 420  degrees of freedom
#(290 observations deleted due to missingness)
#AIC: 399.55

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.MFA), confint(BS.NEFA.0.7_MS.MFA)))

#                     OR     2.5 %     97.5 %
#(Intercept)  0.01281584 0.005242309  0.02900488
#MS.MFA      10.03419566 5.942846457 17.79263277

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 5.9428 & 17.7926
- The Odds Ratio is: 10.0342

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  
  #### BS.NEFA.0.7 ~ MS.NSFA - Testing how the milk's non-saturated fatty acid levels affect the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.NSFA <- glm(BS.NEFA.0.7 ~ MS.NSFA, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.NSFA)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -4.54781    0.35891 -12.671   <2e-16 ***
#  MS.NSFA      0.17664    0.01841   9.596   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 705.87  on 711  degrees of freedom
#Residual deviance: 589.35  on 710  degrees of freedom
#AIC: 593.35

#Number of Fisher Scoring iterations: 5

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.NSFA), confint(BS.NEFA.0.7_MS.NSFA)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.01059033 0.005106129 0.02089631
#MS.NSFA     1.19319713 1.152166560 1.23852422

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.1522 & 1.2385
- The Odds Ratio is: 1.1932

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.Palmeic - Testing how the milk's palmeic fatty acid levels affect the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.Palmeic <- glm(BS.NEFA.0.7 ~ MS.Palmeic, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.Palmeic)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)
#(Intercept)  -0.8471     0.5284  -1.603    0.109
#MS.Palmeic   -0.1317     0.4646  -0.284    0.777

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 492.39  on 421  degrees of freedom
#Residual deviance: 492.31  on 420  degrees of freedom
#(290 observations deleted due to missingness)
#AIC: 496.31

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.Palmeic), confint(BS.NEFA.0.7_MS.Palmeic)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.4286491 0.1531661 1.223459
#MS.Palmeic  0.8765684 0.3447363 2.145834

```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.3447 & 2.1458
- The Odds Ratio is: 0.8766

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.Stearine - Testing how the milk's stearic fatty acid levels affect the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.Stearine <- glm(BS.NEFA.0.7 ~ MS.Stearine, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.Stearine)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -4.7204     0.4901  -9.631  < 2e-16 ***
#  MS.Stearine   6.7658     0.8346   8.107 5.19e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 492.39  on 421  degrees of freedom
#Residual deviance: 403.98  on 420  degrees of freedom
#(290 observations deleted due to missingness)
#AIC: 407.98

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.Stearine), confint(BS.NEFA.0.7_MS.Stearine)))

#                     OR     2.5 %     97.5 %
#(Intercept) 8.911739e-03   0.00326305 2.238222e-02
#MS.Stearine 8.676627e+02 180.10682048 4.781708e+03

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 180.1068 & 4,781.708
- The Odds Ratio is: 867.6627

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ MS.Oleic - Testing how the milk's oleic fatty acid levels affect the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_MS.Oleic <- glm(BS.NEFA.0.7 ~ MS.Oleic, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_MS.Oleic)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -4.1732     0.4123 -10.121   <2e-16 ***
#  MS.Oleic      2.3350     0.2806   8.321   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 492.39  on 421  degrees of freedom
#Residual deviance: 393.17  on 420  degrees of freedom
#(290 observations deleted due to missingness)
#AIC: 397.17

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_MS.Oleic), confint(BS.NEFA.0.7_MS.Oleic)))

#                     OR     2.5 %     97.5 %
#(Intercept)  0.01540308 0.00660423  0.03336427
#MS.Oleic    10.32964624 6.10268125 18.37532923

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 6.1027 & 18.3753
- The Odds Ratio is: 10.3296

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ CE.Fat.Level - Testing how the cow's fat level affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_CE.Fat.Level <- glm(BS.NEFA.0.7 ~ CE.Fat.Level, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_CE.Fat.Level)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -3.14461    0.28221 -11.143  < 2e-16 ***
#  CE.Fat.Level  0.09858    0.01399   7.044 1.86e-12 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 695.56  on 694  degrees of freedom
#Residual deviance: 641.41  on 693  degrees of freedom
#(17 observations deleted due to missingness)
#AIC: 645.41

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_CE.Fat.Level), confint(BS.NEFA.0.7_CE.Fat.Level)))

#                     OR     2.5 %     97.5 %
#(Intercept)  0.04308376 0.02436153 0.07376645
#CE.Fat.Level 1.10360408 1.07426933 1.13496243

```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.0743 & 1.1350
- The Odds Ratio is: 1.1036

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ CE.Temp - Testing how the cow's temperature affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_CE.Temp <- glm(BS.NEFA.0.7 ~ CE.Temp, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_CE.Temp)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)  
#(Intercept) -2.98432    1.74612  -1.709   0.0874 .
#CE.Temp      0.04100    0.04513   0.909   0.3636  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 694.10  on 697  degrees of freedom
#Residual deviance: 693.28  on 696  degrees of freedom
#(14 observations deleted due to missingness)
#AIC: 697.28

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_CE.Temp), confint(BS.NEFA.0.7_CE.Temp)))

#                     OR     2.5 %     97.5 %
#(Intercept) 0.05057411 0.000354967 2.592792
#CE.Temp     1.04185223 0.940866637 1.184720

```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9409 & 1.1847
- The Odds Ratio is: 1.0419

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
  
  
  #### BS.NEFA.0.7 ~ CE.Environ.Temp - Testing how the environmental temperature affects the cow's NEFA levels with a cutoff value
  ```r
#Logistic regression test
BS.NEFA.0.7_CE.Environ.Temp <- glm(BS.NEFA.0.7 ~ CE.Environ.Temp, data = hp2, family = binomial(link=logit))
summary(BS.NEFA.0.7_CE.Environ.Temp)

#Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)     -1.89556    0.28514  -6.648 2.98e-11 ***
#  CE.Environ.Temp  0.02801    0.01547   1.811   0.0702 .  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 663.44  on 672  degrees of freedom
#Residual deviance: 660.13  on 671  degrees of freedom
#(39 observations deleted due to missingness)
#AIC: 664.13

#Number of Fisher Scoring iterations: 4

#Calculating the 95% Confidence interval and the Odds Ratio
exp(cbind(OR = coef(BS.NEFA.0.7_CE.Environ.Temp), confint(BS.NEFA.0.7_CE.Environ.Temp)))

#                     OR     2.5 %     97.5 %
#(Intercept)     0.1502335 0.08465657 0.2593317
#CE.Environ.Temp 1.0284109 0.99785541 1.0603468

```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9979 & 1.0603
- The Odds Ratio is: 1.0284

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">
  
 


--------
## Bi-Variate Statistics - Comparing Factor Variables to BS.NEFA.1.2




--------
## Results



