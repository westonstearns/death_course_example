---
title       : Insert the chapter title here
description : Insert the chapter description here
attachments :

--- type:NormalExercise lang:r xp:100 skills:1 key:e7bdffa0e9
## Death data

This is an example of how our platform works. 

We would instruct the students that a dataset `deathdata` had been loaded in to the environement, as well as, the `ggplot2`, `dplyr` and `tidyr` libraries. 

We give them some background about the data like the data set contains a list of many of the most common causes of death with the number of deaths per cause broken down by the age ranges for each cause. 

We would then give them some instructions. 

Follow the instructiosn below to sample the data set and create a plot to visualize the natue of some of the causes of death. 
*** =instructions
- Print a list of the diseases using the code `deathdata$Casues`
- Create a list of the following causes: `"Breast cancer"`,`"Drowning"`, `"Stroke"`, `"Diabetes mellitus"`. Assign the list to `cause_list`.
- Use the `right_join` function to sample the `deathdata` data set.
- Reshape the data using the `gather` function. Complete the code by filling in the blank with `deathdata_sample`.
- Run the plotting code to visualize the `deathdata_sample`.


*** =hint
- This is where we can offer students hints, like don't forget to put the `deathdata` first in the `right_join` function. 

*** =pre_exercise_code
```{r}
library(dplyr)
library(tidyr)
library(ggplot2)

load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1300/datasets/deathdata.RData"))
deathdata <- data

```

*** =sample_code
```{r}
# Print list of diseases
deathdata$Causes

# Creating a list to sample the dataset
cause_list <- as.data.frame(c("Breast cancer","Drowning", "Stroke", "Diabetes mellitus"))
# Rename the column name
names(cause_list) <- "Causes"

# Sample the deathdata 
deathdata_sample <- right_join(deathdata,cause_list)

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
cause_list <- as.data.frame(c("Breast cancer","Drowning", "Stroke", "Diabetes mellitus"))
# Rename the column name
names(cause_list) <- "Causes"

# Sample the deathdata 
deathdata_sample <- right_join(deathdata,cause_list)

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
--- type:NormalExercise lang:r xp:100 skills:1 key:bcf576415a
## Death data Freestyle

For this exercise the `deathdata` data set has een loaded in the environemnet along with the `ggplot2`, `dplyr` and `tidyr` libraries. 

There is no `sample code` or `solution code`, so you can execute any function or create plots in the `script.R window` and run the code by highlighting the code and pressing `command + enter`. 

The output will show in the `R Console` window. 

When you are finished pressing `submit` will run the exercise and give you a success message. You can then exit out of the success message and continue coding on the same exercise.

*** =instructions
- Explore the source window!


*** =hint
- No hint

*** =pre_exercise_code
```{r}
library(dplyr)
library(tidyr)
library(ggplot2)

load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1300/datasets/deathdata.RData"))
deathdata <- data

```

*** =sample_code
```{r}
# Explore the DataCamp platfom here!

```

*** =solution
```{r}

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_error()
success_msg("Good work freestyling! You can exit out of this message and continue coding, or finish up the exercise by clicking `Course Finished`")
```
