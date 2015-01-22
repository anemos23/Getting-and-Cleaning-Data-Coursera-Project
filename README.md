# Getting-and-Cleaning-Data-Coursera-Project
Getting and Cleaning Data Coursera Project

##This is the R script that creates the tidy data set from the file
##It would require the data to be on your working directory in a file with the name UCI HAR Dataset


library(dplyr)
##read the features list and create a string vector with all the variables names
features <- read.table("~/UCI HAR Dataset/features.txt", stringsAsFactors = FALSE)
features <- features[,2]
features <- make.names(features, unique=TRUE)

##read the set, labels and IDs of the train dataset and combine it in a single data frame
train_set <- read.table("~/UCI HAR Dataset/train/X_train.txt", stringsAsFactors = FALSE)
            colnames(train_set) <- features ##Appropriately labels the data set with descriptive variable names
train_labels <- read.table("~/UCI HAR Dataset/train/Y_train.txt", stringsAsFactors = FALSE)
            colnames(train_labels) <- "Activity"
train_IDs <- read.table("~/UCI HAR Dataset/train/subject_train.txt", stringsAsFactors = FALSE)
            colnames(train_IDs) <- "ID"
train <- cbind(train_IDs, train_labels, train_set)

##read the set, labels and IDs of the test dataset and combine it in a single data frame
test_set <- read.table("~/UCI HAR Dataset/test/X_test.txt", stringsAsFactors = FALSE)
            colnames(test_set) <- features ##Appropriately labels the data set with descriptive variable names
test_labels <- read.table("~/UCI HAR Dataset/test/Y_test.txt", stringsAsFactors = FALSE)
            colnames(test_labels) <- "Activity"
test_IDs <- read.table("~/UCI HAR Dataset/test/subject_test.txt", stringsAsFactors = FALSE)
            colnames(test_IDs) <- "ID"
test <- cbind(test_IDs, test_labels, test_set)

##merge test and train data sets
  df <- rbind(test, train)

##set appropriate descriptive labels of activity
  df$Activity <- as.character(df$Activity)
  df$Activity[df$Activity == "1"] <- "WALKING"
  df$Activity[df$Activity == "2"] <- "WALKING_UPSTAIRS"
  df$Activity[df$Activity == "3"] <- "WALKING_DOWNSTAIRS"
  df$Activity[df$Activity == "4"] <- "SITTING"
  df$Activity[df$Activity == "5"] <- "STANDING"
  df$Activity[df$Activity == "6"] <- "LAYING"

##convert the data fram to a data table
  dt <- tbl_dt(df)

##get the columns that include mean and standard deviation so that those are selected for the final data frame
  mean_columns <- 2 + grep("mean()", features, ignore.case = FALSE, value = FALSE)
  std_columns <- 2 + grep("std", features, ignore.case = TRUE, value = FALSE)
  mean_std_columns <- c(mean_columns, std_columns)

##select the required variables of ID, Activity and mean and std measurements. 
##This includes mean frequency measurements as well - a total of 81 variables including ID and activity. 
  step_4 <- select(dt, ID, Activity, mean_std_columns)

## now we need to re-group the step_4 data and get the means of each column to create the final tidy one
library(plyr)
tidy_tb <- ddply(step_4, .(ID, Activity), numcolwise(mean))
write.table(tidy_tb, file = "~/R/run_analysis.txt", row.names=FALSE)
