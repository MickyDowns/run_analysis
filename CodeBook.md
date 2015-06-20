Run_analysis Code Book
========================================================

##Study Design
Data Collection: Data was collected from the UCI.edu site. That data split smart phone sensor readings across multiple files including test and training files as well as subject, feature and activity files. 

Reading from the article, objective is to determine what activity is being performed across subjects. That is the "y" or dependent factor variable activityLabel (also ActivityName). For this six activity model, I have selected 70 variables according to the following criteria: 

Time domain (“t”) vs. Fourier (“f”) means and std devs:
Time-based data is raw movement data plotted over time. Fourier transformation seeks to isolate periodic, wave-like, oscillations in the data using trigonometric sub-functions (sines, cosines, etc). Given the repetitive nature of movements in the activities to be predicted, I believe Fourier will be more predictive. Therefore, where Time and Fourier options existed, I chose Fourier. Three Time variables don’t have Fourier Transforms (GravityAcc, GravityAccMag and BodyGyroJerk). I included these means and std devs.

Body vs. Gravity means and standard deviations:
When predicting activity, my hypothesis is that measurements inclusive of gravity will better separate activities with similar motions (e.g., walking, walking up stairs, walking down stairs). Therefore, where Gravity and Body are options, I’ve chosen Gravity. 

Acceleration vs. Gyro:
These represent readings from two different sensors (the accelerometer and the gyroscope). Therefore, I included means and std devs for both types of sensor readings.

Jerk readings:
Jerk signals indicate change in the direction of motion. Used in conjunction with means and std devs for continuous movements (Acc and Gyro measures), these will be important ways of discriminating between activities w/ different movement patterns. Therefore, I included Jerk mean and std devs.

##Code Book
Three data files are created: 1. 'masterData.txt': Merged file containing all input data, 2. 'activitySubjectMeans.txt': Means for 39 key features by activity/subject, 3. 'listOfVariables.csv': List of key features. 

Key features chosen are:

1.    activityLabel

2.	activityName

3.	activitySubject

4.	tGravityAccmeanX

5.	tGravityAccmeanY

6.	tGravityAccmeanZ

7.	tGravityAccstdX

8.	tGravityAccstdY

9.	tGravityAccstdZ

10.	tGravityAccMagmean

11.	tGravityAccMagstd

12.	tBodyGyroJerkMagmean

13.	tBodyGyroJerkMagstd

14.	fBodyAccmeanX

15.	fBodyAccmeanY

16.	fBodyAccmeanZ

17.	fBodyAccstdX

18.	fBodyAccstdY

19.	fBodyAccstdZ

20.	fBodyAccJerkmeanX

21.	fBodyAccJerkmeanY

22.	fBodyAccJerkmeanZ

23.	fBodyAccJerkstdX

24.	fBodyAccJerkstdY

25.	fBodyAccJerkstdZ

26.	fBodyGyromeanX

27.	fBodyGyromeanY

28.	fBodyGyromeanZ

29.	fBodyGyrostdX

30.	fBodyGyrostdY

31.	fBodyGyrostdZ

32.	fBodyAccMagmean

33.	fBodyAccMagstd

34.	fBodyBodyAccJerkMagmean

35.	fBodyBodyAccJerkMagstd

36.	fBodyBodyGyroMagmean

37.	fBodyBodyGyroMagstd

38.	fBodyBodyGyroJerkMagmean

39.	fBodyBodyGyroJerkMagstd