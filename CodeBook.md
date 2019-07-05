# Original data description
The original data is available [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip).
It describes its data in various files (`README.txt`, `feature_info.txt`, `features.txt` and `activity_labels.txt`).
It contains variables derived form accelerometer and gyroscope sensor measurements that were
made while different subjects where doing different activities, e.g. sitting of walking. 

# New tidy data description
The output of `run_analysis.R` is the tidy data submitted. That means it contains one observation on each row
and one variable on each column.

The following high level transformation were applied (as required by the project goals):

1. Merge the training and the test sets to create one data set.
2. Extract only the measurements on the mean and standard deviation for each measurement.
3. Apply descriptive activity names to name the activities in the data set
4. Appropriately label the data set with descriptive variable names.
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject. 

For a more detailed description of the transformations applied, see the comments in the `run_analysis.R` file. 

This data has the following variables
* `activity`. A factor describing the activity the subject was doing during the measurement.
* `subject`. An integer that identifies which of the 30 subjects this row's measurements are. 
* All 66 other variables where derived by taking the correspondingly named variable from the input data
and taking the average of all observations grouped by activity and subject. 
Variable names were kept very similar to those in the original data, so their
meaning can be derived from the descriptions found in `features_info.txt`.
E.g. `tBodyAccMeanX` is the average of the `tBodyAcc-mean()-X` feature (described in 
the original data `feature.txt`) across all the measurements for a single user.

The data consists of 180 observations (30 participants * 6 activities) for each of the 68 variables. 

# Original data `feature_info.txt`
For reference, the naming scheme used to describe the varialbes is repeated here from the input data `feature_info.txt` codebook. 

> The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals > (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth > filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals > (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 
> 
> Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also > the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, > tBodyGyroJerkMag). 
> 
> Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, > fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 
> 
> These signals were used to estimate variables of the feature vector for each pattern:  
> '-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
> 
> * tBodyAcc-XYZ
> * tGravityAcc-XYZ
> * tBodyAccJerk-XYZ
> * tBodyGyro-XYZ
> * tBodyGyroJerk-XYZ
> * tBodyAccMag
> * tGravityAccMag
> * tBodyAccJerkMag
> * tBodyGyroMag
> * tBodyGyroJerkMag
> * fBodyAcc-XYZ
> * fBodyAccJerk-XYZ
> * fBodyGyro-XYZ
> * fBodyAccMag
> * fBodyAccJerkMag
> * fBodyGyroMag
> * fBodyGyroJerkMag
> 
> The set of variables that were estimated from these signals are: 
> 
> * mean(): Mean value
> * std(): Standard deviation
> * mad(): Median absolute deviation 
> * max(): Largest value in array
> * min(): Smallest value in array
> * sma(): Signal magnitude area
> * energy(): Energy measure. Sum of the squares divided by the number of values. 
> * iqr(): Interquartile range 
> * entropy(): Signal entropy
> * arCoeff(): Autorregresion coefficients with Burg order equal to 4
> * correlation(): correlation coefficient between two signals
> * maxInds(): index of the frequency component with largest magnitude
> * meanFreq(): Weighted average of the frequency components to obtain a mean frequency
> * skewness(): skewness of the frequency domain signal 
> * kurtosis(): kurtosis of the frequency domain signal 
> * bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
> * angle(): Angle between to vectors.
> 
> Additional vectors obtained by averaging the signals in a signal window sample. These are used on the angle() variable:
> 
> * gravityMean
> * tBodyAccMean
> * tBodyAccJerkMean
> * tBodyGyroMean
> * tBodyGyroJerkMean
> 
> The complete list of variables of each feature vector is available in 'features.txt'