This is the Codebook!

For this project data was downloaded from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
and was stored in a file named UCI HAR Dataset

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. 

In this final tidy data table we have the measurements of 30 subjects (ID = 1:30) across 6 different activity patterns 

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

