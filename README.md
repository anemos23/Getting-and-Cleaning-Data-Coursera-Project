# Getting-and-Cleaning-Data-Coursera-Project
Getting and Cleaning Data Coursera Project
This is the readme file for the course
The purpose of this project is to demonstrate your ability to collect, work with, and clean a data set. The goal is to prepare tidy data that can be used for later analysis.

###Codebook
The codebook.md describes the variables, the data, and any transformations or work that you performed to clean up the data 

###R Script
The run_analysis.R file contains the script that can reproduce the run_analysis.txt file that has been submitted

This is how the files were read and manipulated in order to produce the final tidy data table, starting from downloading the data in the working directory from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

1. The X_train.txt Y.train.txt, subject_train.txt were read with read.table and cbind to create the train data frame
2. The X_test.txt Y.test.txt, subject_test.txt were read with read.table and cbind to create the test data frame
3. The features.txt list was read and subsetted to create a string vector with all the variables names as unique to remove hyphens
4. The train and test data frames were merged with rbind to create one data set
5. The activity variable was subsetted accordingly to reflect the appropriate activity pattern in a descriptive manner
6. The grep function was used to get the indexes of the variables describing mean and standard deviation.
7. The data frame (converted to data table) was subsetted to contain only 81 variables of ID, Activity, and mean and standard deviation variabes using select(dplyr)
8. The final tidy data table was constructed using ddply(plyr) to calculate the average of each variable for each activity and each subject
