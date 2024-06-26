# Chi_Square-test-of-fitness-with-the-Application-of-the-Real_world-Mall_Customer-Shopping-Datasets
In this example, we conducted a chi-square test to determine if there is a significant association between Gender and Spending Score in the Mall Customer dataset.
---
title: "CHISQUARE TEST OF MALL CUSTOMER DATASET"
author: "Langat Erick"
output: pdf
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(
 message = FALSE,
 warning = FALSE,
 echo = FALSE)
```

## 

```{r}
library(tidyverse)
library(report)
library(tidymodels)
```

```{r}
mall_customer <- read.csv("C:/Users/JIT/Downloads/PYTHON TUTORIALS/Mall_Customers.csv")
mall_customer
```

```{r}
cont_table <- table(mall_customer$Gender, mall_customer$Spending.Score..1.100.)
cont_table
```

```{r}
chi_sq <- chisq.test(cont_table)
# Print the results
print(chi_sq)
```

```{r}

```

In this example, we conducted a chi-square test to determine if there is a significant association between Gender and Spending Score in the Mall Customer dataset. The results of the test showed a p-value of 0.03932, which is less than the commonly used threshold of 0.05 for statistical significance. This means that we can reject the null hypothesis that there is no association between Gender and Spending Score in the Mall Customer dataset.

Therefore, we can conclude that there is a significant association between Gender and Spending Score in the Mall Customer dataset. This indicates that the two variables are not independent and there is a relationship between a customer's gender and their spending score. We could further investigate this relationship by conducting additional analyses, such as examining the mean spending score for each gender group or visualizing the relationship using plots or charts.

```{r}
# Calculate the mean spending score for each gender group
mean_spending <- tapply(mall_customer$Spending.Score..1.100., mall_customer$Gender, mean)

# Print the results
mean_spending

```

```{r}
# Create a boxplot of Spending Score by Gender
boxplot(mall_customer$Spending.Score..1.100. ~ mall_customer$Gender,
        xlab = "Gender",
        ylab = "Spending Score",
        col=rainbow(3),
        main = "Box-plot of Spending Score by Gender")

```

Overall, this analysis tells us that there is a significant association between Gender and Spending Score in the Mall Customer data-set, and that female customers tend to have a higher spending score than male customers on average.
