The run_analysis.R script performs the following activities.

1) Donwload the zip file from the http link provided.
2) After download, check if the file already exist. If not exist, unzip the file under folder named "UCI HAR Dataset".
3) read all the file and assign them to the following variable.
   a) features <- features.txt
   b) activities <- activity_labels.txt
   c) subject_test <- subject_test.txt
   d) x_test <- X_test.txt
   e) y_test <- y_test.txt
   f) subject_train <- subject_train.txt
   g) x_train <- X_train.txt
   h) y_train <- y_train.txt

4) Merges the training and the test sets to form one single data set
   a） X <- merge x_train and x_test with rbind() function
   b) Y <- merge y_train and y_test with rbind() function
   c) Subject <- merge subject_train and subject_test with rbind() function
   d) Merged_Data <- merging Subject, Y and X with cbind() function

5) TidayData is created by subsetting Merged_Data, select only columns subject, code and the mean and standard deviation (std) for each measurement
6) Change the columns name in TidyData to be more intuitive.
   a) code replaced by the activities name
   b) All Acc replaced by Accelerometer
   c) All Gyro replaced by Gyroscope
   d) All BodyBody replaced by Body
   e) All Mag replaced by Magnitude
   f) All freq replaced by Freq
   g) All column start with character f replaced by Frequency
   h) All column start with character t replaced by Time
   i) All tBody repalced by TimeBody
   j) All mean replaced by Mean
   k) All std replaced by STD
   l) All angle replaced by Angle
   m) All gravity replaced by Gravity
 
 7) A second data set is created from TidyData with the average of each variable for each activity and each subject.
 8) Data is written to the FinalData.txt file.
