## CodeBook.md

The run_analysis.R script performs downloads and tidies the data set of human activity recognition using smartphones from the machine learning repository of the University of California Irvine as part of the Getting and Cleaning Data Course Project. It also creates a tidy data set with the averages of the means and standard deviations grouped by subject and activity.

### Workspace, package and URL preparations

The lines of code 7-18 set the workspace, load the dplyr package, and assign the .zip and URL paths to file and fileURL for easier access.

### Data set checking, download, and unzipping

The lines of code 20-34 check if the .zip file is present in the workspace. If it isn't, they download it from the provided URL. They also check if the folder is present in the workspace. If it isn't, they unzip it.

### Data frame set up

The lines of code 36-47 assign each of the variables:

- activity (6 observations of 2 variables): Class labels of the 6 types of activities performed by the subjects
- features (561 observations of 2 variables): Features taken from accelerometer and gyroscope readings
- subject_train (7352 observations of 1 variable): Data on 70% of the subjects
- X_train (7352 observations of 561 variables): Features of train data
- y_train (7352 observations of 1 variable): Activities of train data
- subject_test (2947 observations of 1 variable): Data on 30% of the subjects
- X_test (2947 observations of 561 variables): Features of test data
- y_test (2947 observations of 1 variable): Activities of test data

### Merging of data sets

The lines of code 49-55 merge the training and test data sets by corresponding rows and columns.

- subject (10299 observations of 1 variable): Result of merging the subject training and test data frames
- X (10299 observations of 561 variables): Result of merging the feature training and test data frames
- y (10299 observations of 1 variable): Result of merging the activity training and test data frames
- database (10299 observations of 563 variables): Result of mergint the subject, feature, and activity training and test data frames

### Extracting only mean and standard deviation measurements

The lines of code 57-59 extract the mean and standard deviation measurements

- clean_database (10299 observations of 88 variables): Result of selecting only the columns with "mean" and "std" in their names.

### Renaming with descriptive activity names instead of class labels

The lines of code 61-63 renames the class labels with their corresponding activity names according to activity_labels.txt.

### Appropriate labeling of columns with descriptive names

The lines of code 65-73 rename the variable names according to the conventions of the README.txt and features_info.txt.

### Creation of independent data set with the averages of each variable grouped by subject and activity.

The lines of code 75-78 create a new data set with the averages of each variable grouped by subject and activity.

- clean_database2 (180 observations of 88 variables): New data set that shows the averages of each variable grouped by subject and activity.