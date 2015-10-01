Analysis of Smart Device Sensor Output
============
##Summary: Collect, reformat and summarize smart phone sensor data.
Author: Micky Downs

##Abstract:
Facilitate analysis of sensor data taken from smart phones:
1. Merges the training and test sets to create "master" data set.
2. Cleans all column names, reformatting several.
3. Decodes activity label by showing the corresponding activity name.
4. Outputs that file as "masterData.txt".
5. Calculates average for 70 key mean and std dev variables. 
6. Outputs calcs by activity and subject as "activitySubjectMeans.txt".

##Inputs:
1. 'activity_labels.txt': Links the class labels with their activity name.
2. 'train/X_train.txt': Training set.
3. 'train/y_train.txt': Training labels.
4. 'train/subject_train.txt': ID for subject who performed the activity.
5. 'test/X_test.txt': Test set.
6. 'test/y_test.txt': Test labels.
7. 'train/subject_train.txt': ID for subject who performed the activity.
8. 'features.txt': List of all features.

##Outputs:
1. 'masterData.txt': Merged file containing all input data.
2. 'activitySubjectMeans.txt': Means for 70 key features by activity/subject.
3. 'listOfVariables.csv': List of 70 key features.

##Feature (column) Selection Criteria
Reading from the article, objective is to determine what activity is being performed across subjects. That is the "y" or dependent factor variable activityLabel (also ActivityName). For this six activity model, I have selected 70 variables according to the following criteria: 

Time domain (“t”) vs. Fourier (“f”) means and std devs:
Time-based data is raw movement data plotted over time. Fourier transformation seeks to isolate periodic, wave-like, oscillations in the data using trigonometric sub-functions (sines, cosines, etc). Given the repetitive nature of movements in the activities to be predicted, I believe Fourier will be more predictive. Therefore, where Time and Fourier options existed, I chose Fourier. Three Time variables don’t have Fourier Transforms (GravityAcc, GravityAccMag and BodyGyroJerk). I included these means and std devs.

Body vs. Gravity means and standard deviations:
When predicting activity, my hypothesis is that measurements inclusive of gravity will better separate activities with similar motions (e.g., walking, walking up stairs, walking down stairs). Therefore, where Gravity and Body are options, I’ve chosen Gravity. 

Acceleration vs. Gyro:
These represent readings from two different sensors (the accelerometer and the gyroscope). Therefore, I included means and std devs for both types of sensor readings.

Jerk readings:
Jerk signals indicate change in the direction of motion. Used in conjunction with means and std devs for continuous movements (Acc and Gyro measures), these will be important ways of discriminating between activities w/ different movement patterns. Therefore, I included Jerk mean and std devs.

##Column Naming
In all instances, I removed problematic characters (e.g.,: “(“,”)”,”,”,”-“) from column names. Further, I changed and, in some cases, added column names for clarity (e.g.,: activitySubject, activityLabel and activityName). Note: Three sets of input data columns have names that differ from their “features.txt” and “featuresinfo.txt” descriptions. I left these column names "as is"" pending clarification by the author. 

