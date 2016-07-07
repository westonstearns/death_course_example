---
title       : Insert the chapter title here
description : Insert the chapter description here
attachments :

--- type:NormalExercise lang:r xp:100 skills:1 key:e7bdffa0e9
## Death data

The data set is loaded and available so are the libraries...

Sample the data and creat a plot

*** =instructions
- Print a list of the diseases using the code `deathdata$Casues`
- Create a list of the diseases of interest
- sample the data based on those diseases
- reshape the data
- make plot

*** =hint
- hinty hint hint

*** =pre_exercise_code
```{r}
library(dplyr)
library(tidyr)
library(ggplot2)

load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1300/datasets/deathdata.RData"))

```

*** =sample_code
```{r}
# Print list of diseases
deathdata$___

# Creating a list to sample the dataset
cause_list <- as.data.frame(c("___","___", "___", "___"))
# Rename the column name
names(___) <- "Causes"

# Sample the deathdata 
deathdata_sample <- right_join(___,___)

# Making the data into long format
deathdata_long <- gather(deathdata_sample, "ages","deaths", 2:16)

# Plotting the data
ggplot(deathdata_long, aes(Causes,deaths)) + geom_bar(aes(fill = ages),stat = "identity") + theme(axis.text.x = element_text(angle = 60, hjust = 1))

```

*** =solution
```{r}
# Print list of diseases
deathdata$Causes

# Creating a list to sample the dataset
cause_list <- as.data.frame(c("Breast cancer","Hypertensive heart disease", "Stroke", "Diabetes mellitus"))
# Rename the column name
names(Cause_list) <- "Causes"

# Sample the deathdata 
deathdata_sample <- right_join(deathdata,Cause_list)

# Making the data into long format
deathdata_long <- gather(deathdata_sample, "ages","deaths", 2:16)

# Plotting the data
ggplot(deathdata_long, aes(Causes,deaths)) + geom_bar(aes(fill = ages),stat = "identity") + theme(axis.text.x = element_text(angle = 60, hjust = 1))

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_error()
success_msg("Good work!")
```
