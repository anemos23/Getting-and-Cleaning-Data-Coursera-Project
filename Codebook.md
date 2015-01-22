This is the Codebook!

For this project data was downloaded from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
and was stored in a file named UCI HAR Dataset

1. The X_train.txt Y.train.txt, subject_train.txt were read with read.table and cbind to create the train data frame
2. The X_test.txt Y.test.txt, subject_test.txt were read with read.table and cbind to create the test data frame
3. The features.txt list was read and subsetted to create a string vector with all the variables names as unique to remove hyphens
4. The train and test data frames were merged with rbind to create one data set
5. The activity variable was subsetted accordingly to reflect the appropriate activity pattern in a descriptive manner
6. The grep function was used to get the indexes of the variables describing mean and standard deviation.
7. The data frame (converted to data table) was subsetted to contain only 81 variables of ID, Activity, and mean and standard deviation variabes using select(dplyr)
8. The final tidy data table was constructed using ddply(plyr) to calculate the average of each variable for each activity and each subject

In this final tidy data table we have the measurements of 30 subjects (ID = 1:30) across 6 different activity patterns 
1 WALKING
2 WALKING_UPSTAIRS
3 WALKING_DOWNSTAIRS
4 SITTING
5 STANDING
6 LAYING

For each pair of subject-activity we calculate the mean of the measurements across a series of variables. 
The complete list of variables for which the means for each subject-activity were calculated are  below: 

tBodyAcc.mean...X	
tBodyAcc.mean...Y	
tBodyAcc.mean...Z	
tGravityAcc.mean...X	
tGravityAcc.mean...Y	
tGravityAcc.mean...Z	
tBodyAccJerk.mean...X	
tBodyAccJerk.mean...Y	
tBodyAccJerk.mean...Z	
tBodyGyro.mean...X
tBodyGyro.mean...Y	
tBodyGyro.mean...Z	
tBodyGyroJerk.mean...X
tBodyGyroJerk.mean...Y	
tBodyGyroJerk.mean...Z	
tBodyAccMag.mean..	
tGravityAccMag.mean..	
tBodyAccJerkMag.mean..
tBodyGyroMag.mean..	
tBodyGyroJerkMag.mean..	
fBodyAcc.mean...X
fBodyAcc.mean...Y	
fBodyAcc.mean...Z	
fBodyAcc.meanFreq...X	
fBodyAcc.meanFreq...Y
fBodyAcc.meanFreq...Z	
fBodyAccJerk.mean...X	
fBodyAccJerk.mean...Y	
fBodyAccJerk.mean...Z	
fBodyAccJerk.meanFreq...X
fBodyAccJerk.meanFreq...Y	
fBodyAccJerk.meanFreq...Z	
fBodyGyro.mean...X	
fBodyGyro.mean...Y	
fBodyGyro.mean...Z	
fBodyGyro.meanFreq...X	
fBodyGyro.meanFreq...Y	
fBodyGyro.meanFreq...Z	
fBodyAccMag.mean..
fBodyAccMag.meanFreq..
fBodyBodyAccJerkMag.mean..	
fBodyBodyAccJerkMag.meanFreq..	
fBodyBodyGyroMag.mean..	
fBodyBodyGyroMag.meanFreq..	
fBodyBodyGyroJerkMag.mean..	
fBodyBodyGyroJerkMag.meanFreq..	
tBodyAcc.std...X
tBodyAcc.std...Y	
tBodyAcc.std...Z
tGravityAcc.std...X	
tGravityAcc.std...Y
tGravityAcc.std...Z	
tBodyAccJerk.std...X
tBodyAccJerk.std...Y	
tBodyAccJerk.std...Z	
tBodyGyro.std...X	
tBodyGyro.std...Y	
tBodyGyro.std...Z	
tBodyGyroJerk.std...X
tBodyGyroJerk.std...Y	
tBodyGyroJerk.std...Z	
tBodyAccMag.std..
tGravityAccMag.std..	
tBodyAccJerkMag.std..
tBodyGyroMag.std..	
tBodyGyroJerkMag.std..
fBodyAcc.std...X
fBodyAcc.std...Y	
fBodyAcc.std...Z	
fBodyAccJerk.std...X
fBodyAccJerk.std...Y
fBodyAccJerk.std...Z
fBodyGyro.std...X	
fBodyGyro.std...Y	
fBodyGyro.std...Z	
fBodyAccMag.std..	
fBodyBodyAccJerkMag.std..	
fBodyBodyGyroMag.std..	
fBodyBodyGyroJerkMag.std.

