# NEFA-Project
----------
## Table of Contents  
[Introduction](#introduction)  

[Getting Ready For Analysis](#getting-ready-for-analysis)

[List Of All Variables In The Data Set](#list-of-all-the-variables-in-the-data-set)  


--------
## Introduction



--------
## Getting Ready For Analysis
```r
####### Set Working Directory

setwd("C:\\Users\\monie\\Documents\\R\\NEFA-Project")

####### Packages and Libraries

install.packages("tidyverse")
library(tidyverse)

install.packages("dplyr")
library(dplyr)

install.packages("psych")
library(psych)

install.packages("data.table")
library(data.table)

install.packages("lme4")
library(lme4)

####### Save Data sets

load(file="DD3_hp5_single_ISO_per_BLOOD_DATE6_25_19.RData")
hp0 <- hp5
str(hp0)
save(hp0, file="DD3_hp5_single_ISO_per_BLOOD_DATE6_25_19.RData")

load(file="MS_hp9.RData")
hp1 <- hp9
str(hp1)
save(hp1, file="MS_hp9.RData")

load(file="MS_hp9_Log.RData")
hp2 <- hp9
str(hp2)
save(hp2, file="MS_hp9_Log.RData")


####### Edit the Variables

#Rumen Filling (1,2,3,4,5: 1,2 low; 3,4 medium; 5 high)
#Waste Consistency (db original level has to be thin)


# CE.Stom.Fullness: 

hp2$CE.Stom.Fullness.2 <- 0
hp2$CE.Stom.Fullness.2<-as.numeric(hp2$CE.Stom.Fullness.2)
hp2$CE.Stom.Fullness.2[hp0$CD_Pans_Sc==2]<- "low"
hp2$CE.Stom.Fullness.2[hp0$CD_Pans_Sc==3]<- "normal"
hp2$CE.Stom.Fullness.2[hp0$CD_Pans_Sc==4]<- "normal"
hp2$CE.Stom.Fullness.2[hp0$CD_Pans_Sc==5]<- "high"
hp2$CE.Stom.Fullness.2[0]<- "NA"
hp2$CE.Stom.Fullness.2<-as.factor(hp2$CE.Stom.Fullness.2)
hp2$CE.Stom.Fullness <- hp2$CE.Stom.Fullness.2
hp2$CE.Stom.Fullness
hp2$CE.Stom.Fullness.2 <- NULL
str(hp2)

table(hp2$CE.Stom.Fullness)
#0   high    low normal 
#13      4     24    671 


# CE.Waste.Consistency

levels(hp0$CD_Kot_K)
hp2$CE.Waste.Consistency.2 <- 0
hp2$CE.Waste.Consistency.2 <- as.numeric(hp2$CE.Waste.Consistency.2)
hp2$CE.Waste.Consistency.2[hp0$CD_Kot_K=="db"]<- "thin"
hp2$CE.Waste.Consistency.2[hp0$CD_Kot_K=="dick"]<- "thick"
hp2$CE.Waste.Consistency.2[hp0$CD_Kot_K=="sup"]<- "thin"
hp2$CE.Waste.Consistency.2[hp0$CD_Kot_K=="wäs"]<- "thin"
hp2$CE.Waste.Consistency.2[hp0$CD_Kot_K=="mb"]<- "norm"
hp2$CE.Waste.Consistency[hp2$CE.Waste.Consistency=="0"]<- NA
hp2$CE.Waste.Consistency.2 <- as.factor(hp2$CE.Waste.Consistency.2)
hp2$CE.Waste.Consistency <- hp2$CE.Waste.Consistency.2
hp2$CE.Waste.Consistency.2 <- NULL
hp2$CE.Waste.Consistency

table(hp2$CE.Waste.Consistency)
#0  norm thick  thin 
#0   524    53   115 
```
-------
## List Of All Variables In The Data Set

#### Numerical Variables:
BS.NEFA.Log
BS.BHBA.Log
BS.DIM
BS.MS.Date.Diff
Calving.No
Milk.Yield
MS.Milk.Yield
MS.NEFA
MS.BHBA.Log
MS.DIM
MS.Fat
MS.Protein
MS.Lactose
MS.Acetone.Log
MS.Urea
MS.SCC.Log
MS.pH
MS.SFA
MS.PFA
MS.MFA
MS.NSFA
MS.Palmeic
MS.Stearine
MS.Oleic
CE.Fat.Level
CE.Temp
CE.Environ.Temp

#### Factor Variables:
Cow.Breed
Hfr.or.Cow
BS.Month
CE.Skin.Dehydration
CE.Stom.Tension
CE.Stom.Layering
CE.Stom.Fluid.Movement
CE.Stom.Ping
CE.Stom.Fullness
CE.Stom.Noise.Freq
CE.Waste.Consistency
CE.Waste.Digestion
CE.Locomotion.Score
CE.Lame
BS.BHBA.1.2
BS.NEFA.0.7
      
-------
