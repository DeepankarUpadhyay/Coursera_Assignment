This code book will describe the data used in this project, as well as the processing required to create the resulting tidy data set.

Overview
30 volunteers performed 6 different activities while wearing a smartphone. The smartphone captured various data about their movements.

1. Explanation of each file
subject_test : subject IDs for test

subject_train : subject IDs for train

X_test : values of variables in test

X_train : values of variables in train

y_test : activity ID in test

y_train : activity ID in train

activity_labels : Description of activity IDs in y_test and y_train

features : description(label) of each variables in X_test and X_train

dataSet : bind of X_train and X_test

2. Extract only mean() and std()
Create a vector of only mean and std labels, then use the vector to subset dataSet.

MeanStdOnly : a vector of only mean and std labels extracted from 2nd column of features
dataSet : at the end of this step, dataSet will only contain mean and std variables

3. Output tidy data
In this part, dataSet is melted to create tidy data. It will also add [mean of] to each column labels for better description. Finally output the data as "tidy_data.txt"


Processing steps
All of the relevant data files were read into data frames, appropriate column headers were added, and the training and test sets were combined into a single data set.
All feature columns were removed that did not contain the exact string "mean()" or "std()". This left 66 feature columns, plus the subjectID and activity columns.
The activity column was converted from a integer to a factor, using labels describing the activities.
A tidy data set was created containing the mean of each feature for each subject and each activity. Thus, subject #1 has 6 rows in the tidy data set (one row for each activity), and each row contains the mean value for each of the 66 features for that subject/activity combination. Since there are 30 subjects, there are a total of 180 rows.
The tidy data set was output to a CSV file.
