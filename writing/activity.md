# Activity: Statistical tests (The T-test)

## Name

Add Your Name Here

## Instructions

Follow the below mini-tutorial and then complete the following challenge questions.

## Part 1

__Mini Tutorial on Conducting a T-Test on the Iris Dataset Using R Programming__

_Objective_: In this mini-tutorial, we will learn how to perform a statistical T-test using the R programming language, specifically for the Iris dataset which is included with the programming language. Then we will spend a moment to interpret the obtained p-value. Cool, right?!

### Step 1

Clear out the variables and give yourself a clean slate with which to work.

``` {R}
rm(list = ls()) # clear out the variables from memory to make a clean execution of the code.

# If you want to remove all previous plots and clear the console, run the following two lines.
graphics.off() # clear out all plots from previous work.

cat("\014") # clear the console

#library(tidyverse)
# A better way to code...
# Find out if the library is not already installed and\
# if not, install the library and then load it.

if(!require('tidyverse')) {
  install.packages('tidyverse')
  library('tidyverse')
}
```

### Step 2

We load the _Iris_ dataset. We will use the built-in _Iris_ dataset in R for our analysis. To load the dataset, execute the following command:

``` R
data(iris)
```

### Step 3

We prepare the data for analysis. The _Iris_ dataset contains four variables (Sepal Length, Sepal Width, Petal Length, and Petal Width), with three species of irises (_Setosa_, _Versicolor_, and _Virginica_). Let's assume we want to compare the means of two groups (e.g., _Setosa_ vs. _Versicolor_ for Sepal Length). In this example, we will focus on comparing Sepal Length between _Setosa_ and _Versicolor_.

``` {R}
setosa_sepal_length <- iris[iris$Species == "setosa",]$Petal.Length
versicolor_sepal_length <- iris[iris$Species == "versicolor",]$Petal.Length
```

### Step 4

We perform the T-Test. We are ready to perform the T-test on our prepared data. In this case, we will compare the means of _Setosa_ and _Versicolor_ Sepal Length using the `t.test()` function in R.

``` {R}
t_test <- t.test(setosa_sepal_length, versicolor_sepal_length)
```

### Step 5

We Interpret the results. The output of the T-test will include various statistics, but we are primarily interested in the p-value. The p-value indicates the probability that the observed difference between two groups occurred by chance if no real difference exists. If the p-value is less than your chosen significance level (commonly 0.05), you reject the null hypothesis and conclude that there is a statistically significant difference between the means of the two groups:

``` R
print(t_test$p.val) # Prints the p-value
```

For instance, if we get a p-value less than 0.05, we can say that there is evidence to suggest that the mean Sepal Length of _Setosa_ and _Versicolor_ irises are statistically significantly different.

#### Questions

In _clear and meaningful_ language, please respond the the below questions.

1) What are the two hypotheses that we use for this test?

``` {text}
TODO
```

3) Describe the data for each of the two groups is that we are applying to this test. What do the values represent?

``` {text}
TODO
```

4) Run the t-test using the two datasets.

``` {text}
TODO
```

5) What is the _p_-value?

``` {text}
TODO
```
   
6) Which hypothesis is used to form a statistical conclusion?

``` {text}
TODO
```

7) In your own words, describe what this test concludes.

``` {text}
TODO
```

## Part 2

We begin another awesome t-test experiment. We will be using the `mtcars` data set which is included with R.

In the `mtcars` dataset, there is a column called _am_ that concerns the transmission type of the car.  A value of `am == 0` implies an automatic transmission. A value of `am = 1` an manual transmission. In this test, we wish to determine whether there is any difference between the _mpg_ data of both types of transmission for all cars.

1) What are the two hypotheses that we use for this test?

``` {text}
TODO
```

2) Write R code to use the `filter()` function to create two subsets (i.e., two variables, `auto` and `manual`) that contain the _mpg_ data for each type of transmission. Note: use the _am_ column to differentiate each set.

``` {text}
TODO
```

3) Run the t-test using the two datasets.

``` {text}
TODO
```

4) What is the _p_-value?

``` {text}
TODO
```

5) Which hypothesis is used to form a statistical conclusion?

``` {text}
TODO
```

6) In your own words, describe what this test concludes.

``` {text}
TODO
```

(Did you remember to add your name at the top of this document?)