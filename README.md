# Getting and cleaning Data Course project
This repository contains the course project for the [Getting and Cleaning data](https://www.coursera.org/learn/data-cleaning/home/welcome) course on Coursera. 

# Contents
`run_analysis.R` contains all the code to load and transform the data as required.
The code is heavily commented, with each step explaining both what it does
and how it satisfies the project requirements. 

`CodeBook.md` describes the variables, the data and the transformations performed 
to clean up the data. 

# Task
From the project description

> The data linked to from the course website represent data collected from the accelerometers fromthe Samsung Galaxy S smartphone. A full description is > available at the site where the data wasobtained:
> http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones
> 
> Here are the data for the project:
> 
> https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
> 
> You should create one R script called run_analysis.R that does the following.
> 
> 1. Merges the training and the test sets to create one data set.
> 2. Extracts only the measurements on the mean and standard deviation for each measurement.
> 3. Uses descriptive activity names to name the activities in the data set
> 4. Appropriately labels the data set with descriptive variable names.
> 5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject. 