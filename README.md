---
title: "Centerstone 2019-2020 Study"
output:
  pdf_document: default
  html_document: default
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Load the data
```{r}
# Centerstone study 2019-2020
setwd("S:/Indiana Research & Evaluation/Matthew Hanauer/Centerstone_Study_2019_2020")
center_dat_load = read.csv("BelongGive_DataClean_7.20.csv", header = TRUE)
center_dat=  center_dat_load 
head(center_dat)
library(psych)
library(prettyR)
```
Create total scores for INQ and RAS
```{r}
## Reverse score f = 6,g = 7, j=10
## This means reverse score 1,2,5 for second construct
INQ_1_pre = center_dat[,5:9]
INQ_1_pre_des = data.frame(apply(INQ_1_pre, 2, as.factor))
describe(INQ_1_pre_des)

head(INQ_1_pre)
INQ_1_pre = rowMeans(INQ_1_pre, na.rm = TRUE)

INQ_2_pre = center_dat[,10:14]
INQ_2_pre = 8- INQ_2_pre[,c(1,2,5)]
INQ_2_pre_des = data.frame(apply(INQ_2_pre, 2, as.factor))
describe(INQ_2_pre_des)
head(INQ_2_pre)
INQ_2_pre = rowMeans(INQ_2_pre, na.rm = TRUE)


INQ_1_post = center_dat[,100:104]
INQ_1_post_des = data.frame(apply(INQ_1_post, 2, as.factor))
describe(INQ_1_post_des)
head(INQ_1_post)
INQ_1_post = rowMeans(INQ_1_post, na.rm = TRUE)

INQ_2_post = center_dat[,105:109]
INQ_2_post = 8- INQ_2_post[,c(1,2,5)]
INQ_2_post_des = data.frame(apply(INQ_2_post, 2, as.factor))
describe(INQ_2_post_des)
head(INQ_2_post)
INQ_2_post = rowMeans(INQ_2_post, na.rm = TRUE)
head(INQ_1_post)

head(center_dat)
### RAS
## f-m (Personal confidence and hope)    
RAS_1_pre = center_dat[,20:27]
RAS_1_pre_des = data.frame(apply(RAS_1_pre, 2, as.factor))
describe(RAS_1_pre_des)
head(RAS_1_pre)
RAS_1_pre = rowMeans(RAS_1_pre, na.rm = TRUE)
head(RAS_1_pre)

head(center_dat[,15:19])
RAS_1_post = center_dat[,115:122]
head(RAS_1_post)
RAS_1_post_des = data.frame(apply(RAS_1_post, 2, as.factor))
describe(RAS_1_post_des)
head(RAS_1_post)
RAS_1_post = rowMeans(RAS_1_post, na.rm = TRUE)
head(RAS_1_post)


RAS_3_pre = center_dat[,15:19]
RAS_3_pre_des = data.frame(apply(RAS_3_pre, 2, as.factor))
describe(RAS_3_pre_des)
head(RAS_3_pre)
RAS_3_pre = rowMeans(RAS_3_pre, na.rm = TRUE)

RAS_3_post = center_dat[,110:114]
RAS_3_post_des = data.frame(apply(RAS_3_post, 2, as.factor))
describe(RAS_3_post_des)
head(RAS_3_post)
RAS_3_post = rowMeans(RAS_3_post, na.rm = TRUE)

#### RAS 5 No domination by symptoms
RAS_5_pre = center_dat[,28:30]
head(RAS_5_pre)
RAS_5_pre_des = data.frame(apply(RAS_5_pre, 2, as.factor))
describe(RAS_5_pre_des)
head(RAS_5_pre)
RAS_5_pre = rowMeans(RAS_5_pre, na.rm = TRUE)
head(RAS_5_pre)

RAS_5_post = center_dat[,123:125]
head(RAS_5_post)
RAS_5_post_des = data.frame(apply(RAS_5_post, 2, as.factor))
describe(RAS_5_post_des)
head(RAS_5_post)
RAS_5_post = rowMeans(RAS_5_post, na.rm = TRUE)
head(RAS_5_post)

### Lower scores are better
ISLES_1_pre = center_dat[,34:36]
head(center_dat)
ISLES_1_pre_des = data.frame(apply(ISLES_1_pre, 2, as.factor))
describe(ISLES_1_pre_des)
ISLES_1_pre = rowMeans(ISLES_1_pre, na.rm = TRUE)

ISLES_2_pre = center_dat[,37:39]
head(center_dat)
ISLES_2_pre_des = data.frame(apply(ISLES_2_pre, 2, as.factor))
describe(ISLES_2_pre_des)
ISLES_2_pre = rowMeans(ISLES_2_pre, na.rm = TRUE)


ISLES_1_post = center_dat[,132:134]
ISLES_1_post_des = data.frame(apply(ISLES_1_post, 2, as.factor))
describe(ISLES_1_post_des)
ISLES_1_post = rowMeans(ISLES_1_post, na.rm = TRUE)

ISLES_2_post = center_dat[,135:137]
ISLES_2_post_des = data.frame(apply(ISLES_2_post, 2, as.factor))
describe(ISLES_2_post_des)
ISLES_2_post = rowMeans(ISLES_2_post, na.rm = TRUE)


###MILQ higher scores are better factor called Presense
MILQ_pre = center_dat[,40:44]
### Reverse score last question
MILQ_pre[,5] = 8-MILQ_pre[,5]
MILQ_pre_des = data.frame(apply(MILQ_pre, 2, as.factor))
describe(MILQ_pre_des)
head(MILQ_pre)
MILQ_pre = rowMeans(MILQ_pre, na.rm = TRUE)

MILQ_post = center_dat[,127:131]
MILQ_post[,5] = 8-MILQ_post[,5]
MILQ_post_des = data.frame(apply(MILQ_post, 2, as.factor))
describe(MILQ_post_des)
head(MILQ_post)
MILQ_post = rowMeans(MILQ_post, na.rm = TRUE)


### RCS
RCS_pre = center_dat[,56:59]
RCS_pre_des = data.frame(apply(RCS_pre, 2, as.factor))
describe(RCS_pre_des)
head(RCS_pre)
RCS_pre = rowMeans(RCS_pre, na.rm = TRUE)
RCS_pre

RCS_post = center_dat[,151:154]
RCS_post_des = data.frame(apply(RCS_post, 2, as.factor))
describe(RCS_post_des)
head(RCS_post)
RCS_post = rowMeans(RCS_post, na.rm = TRUE)


### BID
BID =  center_dat[,201:206]
BID_des  = data.frame(apply(BID, 2, as.factor))
describe(BID_des)
BID = rowMeans(BID, na.rm = TRUE)
BID

### CSE
center_dat$X5_CSE.a

### TSE_bin

## TSE

### Demos
demos = center_dat[,c(75:78,80,92,97:98)]
demos_fac = data.frame(apply(demos, 2, as.factor))
describe(demos_fac)
female = ifelse(demos$X10_Sex == 2, 1, 0)
demos
veteran = ifelse(demos$X11_Veteran == 2, 1,0)
sexual_minority = ifelse(demos$X12_SO != 3, 1, 0)
hispanic = ifelse(demos$X13_Hisp.Yes.No. == 1, 1, 0)
non_white = ifelse(demos$X14_Race.e == 1, 0,1)
high_school_greater = ifelse(demos$X16_Education > 2, 1, 0)
employed = ifelse(demos$X17_Employment == 2 | demos$X17_Employment == 3, 1, 0)

demos = data.frame(age = demos$X9_Age, veteran, sexual_minority, hispanic, non_white, high_school_greater, employed)


### SIS 1 
# Resolved  = a, b, c, d, g, j, k 
# Planned = e, f, h, i
head(center_dat[,c(49:50,52:53)])
SIS_1_pre = center_dat[,c(49:50,52:53)]
SIS_1_pre_des = data.frame(apply(SIS_1_pre, 2, as.factor))
describe(SIS_1_pre_des)
head(SIS_1_pre)
SIS_1_pre = rowMeans(SIS_1_pre, na.rm = TRUE)
SIS_1_pre

head(center_dat[,c(45:48, 51, 54:55)])
SIS_2_pre = center_dat[,c(45:48, 51, 54:55)]
SIS_2_pre_des = data.frame(apply(SIS_2_pre, 2, as.factor))
describe(SIS_2_pre_des)
head(SIS_2_pre)
SIS_2_pre = rowMeans(SIS_2_pre, na.rm = TRUE)
SIS_2_pre

head(center_dat[,c(159:160, 162:163)])
SIS_1_post = center_dat[,c(159:160, 162:163)]
SIS_1_post_des = data.frame(apply(SIS_1_post, 2, as.factor))
describe(SIS_1_post_des)
head(SIS_1_post)
SIS_1_post = rowMeans(SIS_1_post, na.rm = TRUE)
SIS_1_post

head(center_dat[,c(155:158, 161, 164:165)])
SIS_2_post =center_dat[,c(155:158, 161, 164:165)]
SIS_2_post_des = data.frame(apply(SIS_2_post, 2, as.factor))
describe(SIS_2_post_des)
head(SIS_2_post)
SIS_2_post = rowMeans(SIS_2_post, na.rm = TRUE)
SIS_2_post

### treatment satisfaction CSQ
CSQ =  data.frame(X12_CSQ.a = center_dat$X12_CSQ.a,X12_CSQ.b = center_dat$X12_CSQ.b, X12_CSQ.c = center_dat$X12_CSQ.c)
CSQ_des = data.frame(apply(CSQ, 2, as.factor))
describe(CSQ_des)
head(CSQ_des)
CSQ = rowMeans(CSQ, na.rm = TRUE)
CSQ

### Find these vars Hypothesis 3: Treatment alliance and treatment satisfaction will be positively and uniquely associated with willingness to seek future help at discharge.
WAI
WAI = center_dat[,166:169]
WAI_desc = data.frame(apply(WAI, 2, as.factor))
describe(WAI_desc)
WAI = rowMeans(WAI, na.rm = TRUE)

### CSE
CSE =  center_dat[,138:150]
CSE_desc = data.frame(apply(CSE,2,as.factor))
describe(CSE_desc)
CSE = rowMeans(CSE, na.rm = TRUE)
CSE

### Treatment needs post for those who received the treatment what was average
treat_needs_post = center_dat[,170:195]
## Get whether someone died by suicide or not need to add in 0's and missing for number of attempts
suicide = center_dat$X4_AttemptedSuic

center_dat = data.frame(demos, INQ_1_pre, INQ_2_pre, RAS_1_pre, RAS_3_pre, RAS_5_pre, ISLES_1_pre, ISLES_2_pre, MILQ_pre, RCS_pre, SIS_1_pre, SIS_2_pre, INQ_1_post, INQ_2_post, RAS_1_post, RAS_3_post, RAS_5_post, ISLES_1_post, ISLES_2_post, MILQ_post, RCS_post, SIS_1_post, SIS_2_post, CSQ, BID, WAI, CSE, treat_needs_post, suicide)

```
Descriptives with complete data
```{r}
library(psych)
library(prettyR)
library(installr)
dim(center_dat)
center_dat[,c(2:7,60)] = data.frame(apply(center_dat[,c(2:7,60)],2, as.factor))
desc_stats = describe(center_dat)
desc_stats_numeric = data.frame(desc_stats$Numeric)
desc_stats_numeric = desc_stats_numeric[c(1,4,5),]
desc_stats_numeric
desc_stats_numeric = data.frame(t(desc_stats_numeric))
write.csv(desc_stats_numeric, "desc_stats_numeric.csv", row.names = TRUE)
desc_stats_numeric = read.csv("desc_stats_numeric.csv", header = TRUE)
colnames(desc_stats_numeric)[1] = "variable"
desc_stats_numeric$percent_missing = 1-(as.numeric(desc_stats_numeric$valid.n) / 118)
desc_stats_numeric[,2:5] = format(round(desc_stats_numeric[,2:5], digits=2), nsmall = 2)
desc_stats_numeric
write.csv(desc_stats_numeric, "desc_stats_numeric.csv", row.names = FALSE)

desc_stats_factor = data.frame(desc_stats$Factor) 
desc_stats_factor = t(desc_stats_factor)
desc_stats_factor = format(round(desc_stats_factor, digits=2), nsmall = 2)
write.csv(desc_stats_factor, "desc_stats_factor.csv", row.names = TRUE)
desc_stats_factor = read.csv("desc_stats_factor.csv", header = TRUE)
colnames(desc_stats_factor)[1] = "variable"
desc_stats_factor
write.csv(desc_stats_factor, "desc_stats_factor.csv", row.names = FALSE)

```

Assess missing 
```{r}
head(center_dat)
library(naniar)
miss_var_summary(center_dat)

dim(center_dat)
center_dat_complete = na.omit(center_dat)
dim(center_dat_complete)

quasi_itt =  apply(center_dat, 1, function(x)(sum(is.na(x))))
quasi_itt_dat = data.frame(center_dat,quasi_itt)
describe.factor(quasi_itt_dat$quasi_itt)
### Ten variables and threshold is less than 50% 
dim(quasi_itt_dat)[2]/2
quasi_itt_dat = subset(quasi_itt_dat, quasi_itt < dim(quasi_itt_dat)[2]/2)
dim(center_dat)
dim(quasi_itt_dat)
quasi_itt_dat$quasi_itt = NULL
dim(quasi_itt_dat)

center_dat = quasi_itt_dat
dim(center_dat)


### Scale the CSQ
center_dat$CSQ = scale(center_dat$CSQ)
```
Impute data
```{r}
head(center_dat)
library(Amelia)
a.out = amelia(x = center_dat, m = 5, noms = c("veteran", "sexual_minority", "hispanic", "non_white", "high_school_greater", "employed", "suicide"))
compare.density(a.out, var = "RAS_1_post")
compare.density(a.out, var = "RAS_3_post")
compare.density(a.out, var = "RAS_5_post")
compare.density(a.out, var = "RCS_post")
compare.density(a.out, var = "ISLES_1_post")
compare.density(a.out, var = "ISLES_2_post")
compare.density(a.out, var = "INQ_1_post")
compare.density(a.out, var = "INQ_2_post")
compare.density(a.out, var = "MILQ_post")
compare.density(a.out, var = "SIS_1_post")
compare.density(a.out, var = "SIS_2_post")
overimpute(a.out, var = "SIS_1_post")
overimpute(a.out, var = "SIS_2_post")
impute_dat_loop = a.out$imputations
dim(impute_dat_loop[[1]])
```
Do diff scores with regression, because not random and want to account
```{r}
dim(impute_dat_loop[[1]])
out_diff_dat = list()
head(impute_dat_loop[[1]][8:18])
head(impute_dat_loop[[1]][19:29])

for(i in 1:length(impute_dat_loop)){
  out_diff_dat[[i]] = impute_dat_loop[[i]][8:18]-impute_dat_loop[[1]][19:29]
  colnames(out_diff_dat[[i]]) = c("INQ_1_diff", "INQ_2_diff", "RAS_1_diff", "RAS_3_diff", "RAS_5_diff", "ISLES_1_diff", "ISLES_2_diff", "MILQ_diff", "RCS_diff", "SIS_1_diff", "SIS_2_diff")
  out_diff_dat[[i]] = scale(out_diff_dat[[i]])
  out_diff_dat[[i]] =cbind(impute_dat_loop[[i]], out_diff_dat[[i]])
}
out_diff_dat
### Evaluate normality
out_diff_dat_norm = out_diff_dat[[1]][c(30:32, 34:44)]
hist_results = list() 
qq_results = list()
shap_results = list()
for(i in 1:length(out_diff_dat_norm)){
  hist_results[[i]]= hist(out_diff_dat_norm[[i]], main = paste("Histogram of" , names(out_diff_dat_norm)[[i]]))
  qq_results[[i]] = qqnorm(out_diff_dat_norm[[i]], main = names(out_diff_dat_norm)[[i]])
  shap_results[[i]] = shapiro.test(out_diff_dat_norm[[i]])
}
shap_results
```
Research Question #1: Are novel treatment targets (i.e., perceived burdensomeness, thwarted belongingness, meaning made of stress, goal orientation/hope, resilience-based coping) changing from pre-treatment to post-treatment during standard episodes of care? 

Hypothesis 1: There will be no change in novel treatment target scores from the pre-treatment condition to the post-treatment condition. 
```{r}
 
out_diff_dat_d1 = out_diff_dat[[1]]
out_diff_dat_d1_pre = out_diff_dat_d1[,8:18]

out_diff_dat_d2 = out_diff_dat[[2]]
out_diff_dat_d2_pre = out_diff_dat_d2[,8:18]

out_diff_dat_d3 = out_diff_dat[[3]]
out_diff_dat_d3_pre = out_diff_dat_d3[,8:18]

out_diff_dat_d4 = out_diff_dat[[4]]
out_diff_dat_d4_pre = out_diff_dat_d4[,8:18]

out_diff_dat_d5 = out_diff_dat[[5]]
out_diff_dat_d5_pre = out_diff_dat_d5[,8:18]

out_diff_dat_d1 = out_diff_dat[[1]]
out_diff_dat_d1_post = out_diff_dat_d1[,19:29]

out_diff_dat_d2 = out_diff_dat[[2]]
out_diff_dat_d2_post = out_diff_dat_d2[,19:29]

out_diff_dat_d3 = out_diff_dat[[3]]
out_diff_dat_d3_post = out_diff_dat_d3[,19:29]

out_diff_dat_d4 = out_diff_dat[[4]]
out_diff_dat_d4_post = out_diff_dat_d4[,19:29]

out_diff_dat_d5 = out_diff_dat[[5]]
out_diff_dat_d5_post = out_diff_dat_d5[,19:29]

library(effsize)
center_results_d1 = list()
for(i in 1:length(out_diff_dat_d1_post)){
  center_results_d1[[i]]= cohen.d(out_diff_dat_d1_post[[i]], out_diff_dat_d1_pre[[i]], paired = TRUE, conf.level = .95)
  center_results_d1[[i]] = center_results_d1[[i]][c(3,5)]
}
center_results_d1
center_results_d1 = unlist(center_results_d1)
center_results_d1 = matrix(center_results_d1, ncol = 3, byrow = TRUE)
center_results_d1 = data.frame(center_results_d1)
center_results_d1 = round(center_results_d1, 3)
center_results_d1
colnames(center_results_d1) = c("cohen_d", "lower", "upper")
center_results_d1

center_results_d2 = list()
for(i in 1:length(out_diff_dat_d1_post)){
  center_results_d2[[i]]= cohen.d(out_diff_dat_d2_post[[i]], out_diff_dat_d2_pre[[i]], paired = TRUE, conf.level = .95)
  center_results_d2[[i]] = center_results_d2[[i]][c(3,5)]
}
center_results_d2
center_results_d2
center_results_d2 = unlist(center_results_d2)
center_results_d2 = matrix(center_results_d2, ncol = 3, byrow = TRUE)
center_results_d2 = data.frame(center_results_d2)
center_results_d2 = round(center_results_d2, 3)
center_results_d2
colnames(center_results_d2) = c("cohen_d", "lower", "upper")
center_results_d2

center_results_d3 = list()
for(i in 1:length(out_diff_dat_d1_post)){
  center_results_d3[[i]]= cohen.d(out_diff_dat_d3_post[[i]], out_diff_dat_d3_pre[[i]], paired = TRUE, conf.level = .95)
  center_results_d3[[i]] = center_results_d3[[i]][c(3,5)]
}
center_results_d3
center_results_d3
center_results_d3 = unlist(center_results_d3)
center_results_d3 = matrix(center_results_d3, ncol = 3, byrow = TRUE)
center_results_d3 = data.frame(center_results_d3)
center_results_d3 = round(center_results_d3, 3)
center_results_d3
colnames(center_results_d3) = c("cohen_d", "lower", "upper")
center_results_d3

center_results_d4 = list()
for(i in 1:length(out_diff_dat_d1_post)){
  center_results_d4[[i]]= cohen.d(out_diff_dat_d4_post[[i]], out_diff_dat_d4_pre[[i]], paired = TRUE, conf.level = .95)
  center_results_d4[[i]] = center_results_d4[[i]][c(3,5)]
}
center_results_d4
center_results_d4
center_results_d4 = unlist(center_results_d4)
center_results_d4 = matrix(center_results_d4, ncol = 3, byrow = TRUE)
center_results_d4 = data.frame(center_results_d4)
center_results_d4 = round(center_results_d4, 3)
center_results_d4
colnames(center_results_d4) = c("cohen_d", "lower", "upper")
center_results_d4

center_results_d5 = list()
for(i in 1:length(out_diff_dat_d1_post)){
  center_results_d5[[i]]= cohen.d(out_diff_dat_d5_post[[i]], out_diff_dat_d5_pre[[i]], paired = TRUE, conf.level = .95)
  center_results_d5[[i]] = center_results_d5[[i]][c(3,5)]
}
center_results_d5
center_results_d5
center_results_d5 = unlist(center_results_d5)
center_results_d5 = matrix(center_results_d5, ncol = 3, byrow = TRUE)
center_results_d5 = data.frame(center_results_d5)
center_results_d5 = round(center_results_d5, 3)
center_results_d5
colnames(center_results_d5) = c("cohen_d", "lower", "upper")
center_results_d5


center_results_cohen_d = data.frame(cohen_d1 = center_results_d1$cohen_d, cohen_d2 = center_results_d2$cohen_d, cohen_d3 = center_results_d3$cohen_d, cohen_d4 = center_results_d4$cohen_d, cohen_d5 = center_results_d5$cohen_d)
center_results_cohen_d = rowMeans(center_results_cohen_d)
center_results_cohen_d

center_results_upper = data.frame(upper1 = center_results_d1$upper, upper2 = center_results_d2$upper, upper3 = center_results_d3$upper, upper4 = center_results_d4$upper, upper5 = center_results_d5$upper)
center_results_upper = rowMeans(center_results_upper)
center_results_upper

center_results_lower = data.frame(lower1 = center_results_d1$lower, lower2 = center_results_d2$lower, lower3 = center_results_d3$lower, lower4 = center_results_d4$lower, lower5 = center_results_d5$lower)
center_results_lower = rowMeans(center_results_lower)
center_results_lower

center_results = data.frame(cohen_d = center_results_cohen_d, upper = center_results_upper, lower = center_results_lower)
center_results = round(center_results, 2)
center_results$cohen_d = ifelse(center_results$upper > 0 & center_results$lower < 0, center_results$cohen_d, paste0(center_results$cohen_d, "*"))
center_results$ci_95 = paste0(center_results$lower, sep = ",", center_results$upper)
center_results[,2:3] = NULL
head(out_diff_dat)
center_results

outcomes = c("Perceived Burdensomeness", "Thwarted Belongingness", "Personal confidence and hope", "Goal and Success Orientation", "No domination by symptoms", "Comprehensibility", "Footing in the world", "MILQ", "RCS", "Suicidal Ideation", "Resolved plans and preparations")
center_results = data.frame(outcomes, center_results)

write.csv(center_results, "center_results.csv", row.names = FALSE)


```
Research Question #2: Are novel treatment targets (i.e., perceived burdensomeness, thwarted belongingness, meaning made of stress, meaning in life, goal orientation/hope coping self-efficacy, treatment alliance, treatment satisfaction) associated with episode of care outcomes (i.e., suicide risk, willingness to seek help, intentions to follow-through on discharge plans) at discharge? (Changed to change scores related to each other) 

Hypothesis 1: Perceived burdensomeness and thwarted belongingness will be positively and uniquely associated with suicide risk (i.e., ideation, resolved plans/preparation) at discharge. 

Hypothesis 2: Meaning made of stress, meaning in life, coping self-efficacy, goal orientation/hope, alliance, and treatment satisfaction will be negatively and uniquely associated with suicide risk (i.e., ideation, resolved plans and preparation) at discharge. 

(Add new vars above to global data set)

Sucidial Ideation regression
```{r}

### Regression analysis
regout_sis_1 = list()
regout_sis_1_sum = list()
parsout_sis_1 = list()
sesout_sis_1 = list()
import_sis_1 = list()
vif_sis_1 = list()
library(relaimpo)
head(out_diff_dat[[1]][,34:44])
out_diff_dat_reg = list()
for(i in 1:length(out_diff_dat)){
  out_diff_dat_reg[[i]] =out_diff_dat[[i]][,34:44]
}
out_diff_dat_reg[[1]]

for(i in 1:length(out_diff_dat_reg)){
  regout_sis_1[[i]] = lm(SIS_1_diff ~ INQ_1_diff + INQ_2_diff + RAS_1_diff + RAS_3_diff+ RAS_5_diff + ISLES_1_diff + ISLES_2_diff + MILQ_diff + RCS_diff, data = out_diff_dat_reg[[i]])
  regout_sis_1_sum[[i]] = summary(regout_sis_1[[i]])
  import_sis_1[[i]] = calc.relimp(regout_sis_1[[i]])
  import_sis_1[[i]] = import_sis_1[[i]]@lmg
  parsout_sis_1[[i]] = regout_sis_1_sum[[i]]$coefficients[,1]
  sesout_sis_1[[i]] = regout_sis_1_sum[[i]]$coefficients[,2]
  vif_sis_1[[i]] = vif(regout_sis_1[[i]])
}
vif_sis_1
#10 cols
parsout_sis_1 = unlist(parsout_sis_1) 
parsout_sis_1 = matrix(parsout_sis_1, ncol = 10, byrow = TRUE)
parsout_sis_1

sesout_sis_1 = unlist(sesout_sis_1)
sesout_sis_1 = matrix(sesout_sis_1, ncol = 10, byrow = TRUE)
sesout_sis_1

pars_sesout_sis_1 = mi.meld(parsout_sis_1, sesout_sis_1)
t_stat_reg_sis_1 =  pars_sesout_sis_1$q.mi / pars_sesout_sis_1$se.mi
p_values_reg_sis_1 = 2*pt(-abs(t_stat_reg_sis_1), df = dim(out_diff_dat_corr[[1]])[1]-10)
p_values_reg_sis_1 = format(round(p_values_reg_sis_1, digits=3), nsmall = 2)
p_values_reg_sis_1
p_values_reg_sis_1
critical_t_reg_sis_1 = abs(qt(0.05/2, dim(out_diff_dat_corr[[1]])[1]-10))
critical_t_reg_sis_1
upper_reg_sis_1 = pars_sesout_sis_1$q.mi +(critical_t_reg_sis_1*pars_sesout_sis_1$se.mi)
upper_reg_sis_1 = format(round(upper_reg_sis_1, digits=2), nsmall = 2)
upper_reg_sis_1
lower_reg_sis_1 = pars_sesout_sis_1$q.mi - (critical_t_reg_sis_1*pars_sesout_sis_1$se.mi)
lower_reg_sis_1 = format(round(lower_reg_sis_1, digits=2), nsmall = 2)
ci_95_sis_1 = paste0(upper_reg_sis_1, sep = ",", lower_reg_sis_1)
ci_95_sis_1
import_sis_1 = unlist(import_sis_1)
import_sis_1 = matrix(import_sis_1, ncol = 9, byrow = TRUE)
import_sis_1 = colMeans(import_sis_1)
import_sis_1 

reg_results_sis_1 = data.frame(par_est = t(pars_sesout_sis_1$q.mi), se = t(pars_sesout_sis_1$se.mi), p_value = t(p_values_reg_sis_1), ci_95_sis_1)
reg_results_sis_1
reg_results_sis_1[,1:2] = format(round(reg_results_sis_1[,1:2], digits=2), nsmall = 2)
reg_results_sis_1$var_names = c("Intercept", colnames(out_diff_dat_reg[[1]])[1:9])
reg_results_sis_1 = data.frame(var_names = reg_results_sis_1$var_names, reg_results_sis_1[,1:4])
typeof(reg_results_sis_1$p_value)

write.csv(reg_results_sis_1, "reg_results_sis_1.csv", row.names = FALSE)
reg_results_sis_1 = read.csv("reg_results_sis_1.csv", header = TRUE)
reg_results_sis_1$var_names = as.character(reg_results_sis_1$var_names)

reg_results_sis_1$var_names = ifelse(reg_results_sis_1$p_value < .05, paste0(reg_results_sis_1$var_names, sep = "*"), reg_results_sis_1$var_names)
reg_results_sis_1$p_value = ifelse(reg_results_sis_1$p_value ==.000, "<.001", reg_results_sis_1$p_value)
reg_results_sis_1 = reg_results_sis_1[-c(1),]
reg_results_sis_1$import_sis_1 = import_sis_1
reg_results_sis_1$import_sis_1 = format(round(reg_results_sis_1$import_sis_1, digits=2), nsmall = 2)
reg_results_sis_1
write.csv(reg_results_sis_1, "reg_results_sis_1.csv", row.names  = FALSE)
```
Resolved plans
```{r}
### Regression analysis
regout_sis_2 = list()
regout_sis_2_sum = list()
parsout_sis_2 = list()
sesout_sis_2 = list()
import_sis_2 = list()
vif_sis_2 = list()
library(relaimpo)
head(out_diff_dat[[1]][,34:44])
out_diff_dat_reg = list()
for(i in 1:length(out_diff_dat)){
  out_diff_dat_reg[[i]] =out_diff_dat[[i]][,34:44]
}
out_diff_dat_reg[[1]]

for(i in 1:length(out_diff_dat_reg)){
  regout_sis_2[[i]] = lm(SIS_2_diff ~ INQ_1_diff + INQ_2_diff + RAS_1_diff + RAS_3_diff+ RAS_5_diff + ISLES_1_diff + ISLES_2_diff + MILQ_diff + RCS_diff, data = out_diff_dat_reg[[i]])
  regout_sis_2_sum[[i]] = summary(regout_sis_2[[i]])
  import_sis_2[[i]] = calc.relimp(regout_sis_2[[i]])
  import_sis_2[[i]] = import_sis_2[[i]]@lmg
  parsout_sis_2[[i]] = regout_sis_2_sum[[i]]$coefficients[,1]
  sesout_sis_2[[i]] = regout_sis_2_sum[[i]]$coefficients[,2]
  vif_sis_2[[i]] = vif(regout_sis_2[[i]])
}
vif_sis_2
#10 cols
parsout_sis_2 = unlist(parsout_sis_2) 
parsout_sis_2 = matrix(parsout_sis_2, ncol = 10, byrow = TRUE)
parsout_sis_2

sesout_sis_2 = unlist(sesout_sis_2)
sesout_sis_2 = matrix(sesout_sis_2, ncol = 10, byrow = TRUE)
sesout_sis_2

pars_sesout_sis_2 = mi.meld(parsout_sis_2, sesout_sis_2)
t_stat_reg_sis_2 =  pars_sesout_sis_2$q.mi / pars_sesout_sis_2$se.mi
p_values_reg_sis_2 = 2*pt(-abs(t_stat_reg_sis_2), df = dim(out_diff_dat_corr[[1]])[1]-10)
p_values_reg_sis_2 = format(round(p_values_reg_sis_2, digits=3), nsmall = 2)
p_values_reg_sis_2
p_values_reg_sis_2
critical_t_reg_sis_2 = abs(qt(0.05/2, dim(out_diff_dat_corr[[1]])[1]-10))
critical_t_reg_sis_2
upper_reg_sis_2 = pars_sesout_sis_2$q.mi +(critical_t_reg_sis_2*pars_sesout_sis_2$se.mi)
upper_reg_sis_2 = format(round(upper_reg_sis_2, digits=2), nsmall = 2)
upper_reg_sis_2
lower_reg_sis_2 = pars_sesout_sis_2$q.mi - (critical_t_reg_sis_2*pars_sesout_sis_2$se.mi)
lower_reg_sis_2 = format(round(lower_reg_sis_2, digits=2), nsmall = 2)
ci_95_sis_2 = paste0(upper_reg_sis_2, sep = ",", lower_reg_sis_2)
ci_95_sis_2
import_sis_2 = unlist(import_sis_2)
import_sis_2 = matrix(import_sis_2, ncol = 9, byrow = TRUE)
import_sis_2 = colMeans(import_sis_2)
import_sis_2 

reg_results_sis_2 = data.frame(par_est = t(pars_sesout_sis_2$q.mi), se = t(pars_sesout_sis_2$se.mi), p_value = t(p_values_reg_sis_2), ci_95_sis_2)
reg_results_sis_2
reg_results_sis_2[,1:2] = format(round(reg_results_sis_2[,1:2], digits=2), nsmall = 2)
reg_results_sis_2$var_names = c("Intercept", colnames(out_diff_dat_reg[[1]])[1:9])
reg_results_sis_2 = data.frame(var_names = reg_results_sis_2$var_names, reg_results_sis_2[,1:4])
typeof(reg_results_sis_2$p_value)

write.csv(reg_results_sis_2, "reg_results_sis_2.csv", row.names = FALSE)
reg_results_sis_2 = read.csv("reg_results_sis_2.csv", header = TRUE)
reg_results_sis_2$var_names = as.character(reg_results_sis_2$var_names)

reg_results_sis_2$var_names = ifelse(reg_results_sis_2$p_value < .05, paste0(reg_results_sis_2$var_names, sep = "*"), reg_results_sis_2$var_names)
reg_results_sis_2$p_value = ifelse(reg_results_sis_2$p_value ==.000, "<.001", reg_results_sis_2$p_value)
reg_results_sis_2 = reg_results_sis_2[-c(1),]
reg_results_sis_2$import_sis_2 = import_sis_2
reg_results_sis_2$import_sis_2 = format(round(reg_results_sis_2$import_sis_2, digits=2), nsmall = 2)
reg_results_sis_2

write.csv(reg_results_sis_2, "reg_results_sis_2.csv", row.names = FALSE)
```


Hypothesis 3: Treatment alliance and treatment satisfaction will be positively and uniquely associated with willingness to seek future help at discharge. 

Don't know what this is: willingness to seek future help at discharge
```{r}



```
Hypothesis 4:  Treatment alliance and treatment satisfaction will be positively and uniquely associated with intention to follow-through on discharge plans. 
```{r}
### Regression analysis
regout_hyp_4 = list()
regout_hyp_4_sum = list()
parsout_hyp_4 = list()
sesout_hyp_4 = list()
import_hyp_4 = list()
vif_hyp_4 = list()

for(i in 1:length(out_diff_dat_reg)){
  regout_hyp_4[[i]] = lm(BID ~ CSQ + WAI, data = out_diff_dat[[i]])
  regout_hyp_4_sum[[i]] = summary(regout_hyp_4[[i]])
  import_hyp_4[[i]] = calc.relimp(regout_hyp_4[[i]])
  import_hyp_4[[i]] = import_hyp_4[[i]]@lmg
  parsout_hyp_4[[i]] = regout_hyp_4_sum[[i]]$coefficients[,1]
  sesout_hyp_4[[i]] = regout_hyp_4_sum[[i]]$coefficients[,2]
  vif_hyp_4[[i]] = vif(regout_hyp_4[[i]])
}
vif_hyp_4
#3 cols
parsout_hyp_4 = unlist(parsout_hyp_4) 
parsout_hyp_4 = matrix(parsout_hyp_4, ncol = 3, byrow = TRUE)
parsout_hyp_4

sesout_hyp_4 = unlist(sesout_hyp_4)
sesout_hyp_4 = matrix(sesout_hyp_4, ncol = 3, byrow= TRUE)
sesout_hyp_4

pars_sesout_hyp_4 = mi.meld(parsout_hyp_4, sesout_hyp_4)
t_stat_reg_hyp_4 =  pars_sesout_hyp_4$q.mi / pars_sesout_hyp_4$se.mi
p_values_reg_hyp_4 = 2*pt(-abs(t_stat_reg_hyp_4), df = dim(out_diff_dat_corr[[1]])[1]-10)
p_values_reg_hyp_4 = format(round(p_values_reg_hyp_4, digits=3), nsmall = 2)
p_values_reg_hyp_4
p_values_reg_hyp_4
critical_t_reg_hyp_4 = abs(qt(0.05/2, dim(out_diff_dat_corr[[1]])[1]-10))
critical_t_reg_hyp_4
upper_reg_hyp_4 = pars_sesout_hyp_4$q.mi +(critical_t_reg_hyp_4*pars_sesout_hyp_4$se.mi)
upper_reg_hyp_4 = format(round(upper_reg_hyp_4, digits=2), nsmall = 2)
upper_reg_hyp_4
lower_reg_hyp_4 = pars_sesout_hyp_4$q.mi - (critical_t_reg_hyp_4*pars_sesout_hyp_4$se.mi)
lower_reg_hyp_4 = format(round(lower_reg_hyp_4, digits=2), nsmall = 2)
ci_95_hyp_4 = paste0(upper_reg_hyp_4, sep = ",", lower_reg_hyp_4)
ci_95_hyp_4
import_hyp_4 = unlist(import_hyp_4)
import_hyp_4 = matrix(import_hyp_4, ncol = 2, byrow = TRUE)
import_hyp_4 = colMeans(import_hyp_4)
import_hyp_4 

reg_results_hyp_4 = data.frame(par_est = t(pars_sesout_hyp_4$q.mi), se = t(pars_sesout_hyp_4$se.mi), p_value = t(p_values_reg_hyp_4), ci_95_hyp_4)
reg_results_hyp_4
reg_results_hyp_4[,1:2] = format(round(reg_results_hyp_4[,1:2], digits=2), nsmall = 2)
reg_results_hyp_4$var_names = c("Intercept", "CSQ", "WAI")
reg_results_hyp_4 = data.frame(var_names = reg_results_hyp_4$var_names, reg_results_hyp_4[,1:4])
reg_results_hyp_4

write.csv(reg_results_hyp_4, "reg_results_hyp_4.csv", row.names = FALSE)
reg_results_hyp_4 = read.csv("reg_results_hyp_4.csv", header = TRUE)
reg_results_hyp_4$var_names = as.character(reg_results_hyp_4$var_names)
reg_results_hyp_4

reg_results_hyp_4$var_names = ifelse(reg_results_hyp_4$p_value < .05, paste0(reg_results_hyp_4$var_names, sep = "*"), reg_results_hyp_4$var_names)
reg_results_hyp_4$p_value = ifelse(reg_results_hyp_4$p_value ==.000, "<.001", reg_results_hyp_4$p_value)
reg_results_hyp_4 = reg_results_hyp_4[-c(1),]
reg_results_hyp_4$par_est = format(round(reg_results_hyp_4$par_est, digits=2), nsmall = 2) 
reg_results_hyp_4
reg_results_hyp_4$import_hyp_4 = import_hyp_4
reg_results_hyp_4$import_hyp_4 = format(round(reg_results_hyp_4$import_hyp_4, digits=2), nsmall = 2)
reg_results_hyp_4

write.csv(reg_results_hyp_4, "reg_results_hyp_4.csv", row.names = FALSE)

```
Hypothesis 1: Perceived burdensomeness, thwarted belongingness, and meaning made of stress will contribute the most variance to suicide risk status scores at discharge. 
Going to check all of them
```{r}
### Regression analysis
regout_r3_hyp_1 = list()
regout_r3_hyp_1_sum = list()
parsout_r3_hyp_1 = list()
sesout_r3_hyp_1 = list()
import_r3_hyp_1 = list()
vif_r3_hyp_1 = list()

for(i in 1:length(out_diff_dat)){
  regout_r3_hyp_1[[i]] = glm(suicide ~ INQ_1_diff + INQ_2_diff + RAS_1_diff + ISLES_1_diff + ISLES_2_diff + MILQ_diff + SIS_1_diff+ SIS_2_diff, data = out_diff_dat[[i]], family = binomial()) 
  regout_r3_hyp_1_sum[[i]] = summary(regout_r3_hyp_1[[i]])
  #import_r3_hyp_1[[i]] = calc.relimp(regout_r3_hyp_1[[i]])
  #import_r3_hyp_1[[i]] = import_r3_hyp_1[[i]]@lmg
  parsout_r3_hyp_1[[i]] = regout_r3_hyp_1_sum[[i]]$coefficients[,1]
  parsout_r3_hyp_1[[i]] = exp(parsout_r3_hyp_1[[i]])
  sesout_r3_hyp_1[[i]] = regout_r3_hyp_1_sum[[i]]$coefficients[,2]
  sesout_r3_hyp_1[[i]] = exp(sesout_r3_hyp_1[[i]])
  vif_r3_hyp_1[[i]] = vif(regout_r3_hyp_1[[i]])
}
vif_r3_hyp_1
#3 cols
parsout_r3_hyp_1 = unlist(parsout_r3_hyp_1) 
parsout_r3_hyp_1 = matrix(parsout_r3_hyp_1, ncol = 9, byrow = TRUE)
parsout_r3_hyp_1

sesout_r3_hyp_1 = unlist(sesout_r3_hyp_1)
sesout_r3_hyp_1 = matrix(sesout_r3_hyp_1, ncol = 9, byrow= TRUE)
sesout_r3_hyp_1

pars_sesout_r3_hyp_1 = mi.meld(parsout_r3_hyp_1, sesout_r3_hyp_1)
t_stat_reg_r3_hyp_1 =  pars_sesout_r3_hyp_1$q.mi / pars_sesout_r3_hyp_1$se.mi
p_values_reg_r3_hyp_1 = 2*pt(-abs(t_stat_reg_r3_hyp_1), df = dim(out_diff_dat_corr[[1]])[1]-9)
p_values_reg_r3_hyp_1 = format(round(p_values_reg_r3_hyp_1, digits=3), nsmall = 2)
p_values_reg_r3_hyp_1
p_values_reg_r3_hyp_1
critical_t_reg_r3_hyp_1 = abs(qt(0.05/2, dim(out_diff_dat_corr[[1]])[1]-10))
critical_t_reg_r3_hyp_1
upper_reg_r3_hyp_1 = pars_sesout_r3_hyp_1$q.mi +(critical_t_reg_r3_hyp_1*pars_sesout_r3_hyp_1$se.mi)
upper_reg_r3_hyp_1 = format(round(upper_reg_r3_hyp_1, digits=2), nsmall = 2)
upper_reg_r3_hyp_1
lower_reg_r3_hyp_1 = pars_sesout_r3_hyp_1$q.mi - (critical_t_reg_r3_hyp_1*pars_sesout_r3_hyp_1$se.mi)
lower_reg_r3_hyp_1 = format(round(lower_reg_r3_hyp_1, digits=2), nsmall = 2)
ci_95_r3_hyp_1 = paste0(upper_reg_r3_hyp_1, sep = ",", lower_reg_r3_hyp_1)
ci_95_r3_hyp_1
#import_r3_hyp_1 = unlist(import_r3_hyp_1)
#import_r3_hyp_1 = matrix(import_r3_hyp_1, ncol = 2, byrow = TRUE)
#import_r3_hyp_1 = colMeans(import_r3_hyp_1)
#import_r3_hyp_1 

reg_results_r3_hyp_1 = data.frame(par_est = t(pars_sesout_r3_hyp_1$q.mi), se = t(pars_sesout_r3_hyp_1$se.mi), p_value = t(p_values_reg_r3_hyp_1), ci_95_r3_hyp_1)
reg_results_r3_hyp_1
reg_results_r3_hyp_1[,1:2] = format(round(reg_results_r3_hyp_1[,1:2], digits=2), nsmall = 2)
reg_results_r3_hyp_1$var_names = c(names(regout_r3_hyp_1[[1]]$coefficients))
reg_results_r3_hyp_1 = data.frame(var_names = reg_results_r3_hyp_1$var_names, reg_results_r3_hyp_1[,1:4])
reg_results_r3_hyp_1

write.csv(reg_results_r3_hyp_1, "reg_results_r3_hyp_1.csv", row.names = FALSE)
reg_results_r3_hyp_1 = read.csv("reg_results_r3_hyp_1.csv", header = TRUE)
reg_results_r3_hyp_1$var_names = as.character(reg_results_r3_hyp_1$var_names)
reg_results_r3_hyp_1

reg_results_r3_hyp_1$var_names = ifelse(reg_results_r3_hyp_1$p_value < .05, paste0(reg_results_r3_hyp_1$var_names, sep = "*"), reg_results_r3_hyp_1$var_names)
reg_results_r3_hyp_1$p_value = ifelse(reg_results_r3_hyp_1$p_value ==.000, "<.001", reg_results_r3_hyp_1$p_value)
reg_results_r3_hyp_1 = reg_results_r3_hyp_1[-c(1),]
reg_results_r3_hyp_1$par_est = format(round(reg_results_r3_hyp_1$par_est, digits=2), nsmall = 2) 
reg_results_r3_hyp_1
#reg_results_r3_hyp_1$import_r3_hyp_1 = import_r3_hyp_1
#reg_results_r3_hyp_1$import_r3_hyp_1 = format(round(reg_results_r3_hyp_1$import_r3_hyp_1, digits=2), nsmall = 2)
reg_results_r3_hyp_1

write.csv(reg_results_r3_hyp_1, "reg_results_r3_hyp_1.csv", row.names = FALSE)


```






