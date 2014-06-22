getting-and-cleaning-data-assignment
====================================

## run_analysis.R

This script does the following:

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive activity names. 
5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject. 

## Process

1. For both the test and train datasets, create a temporary dataset:
    1. Extract the mean and standard deviation features (listed in CodeBook.md, section 'Extracted Features'). This is the `values` table.
    2. Get the list of activities.
    3. Put the activity *labels* (not numbers) into the `values` table.
    4. Get the list of subjects.
    5. Put the subject IDs into the `values` table.
2. Join the test and train temporary datasets.
3. Put each variable on its own row.
4. Rejoin the entire table, keying on subject/acitivity pairs, applying the mean function to each vector of values in each subject/activity pair. This is the tidy dataset.
5. Save the tidy as a file in the folder where the original data was stored.

## Tidy Data

The resulting tidy dataset is in this repository at: `data/tidy.txt` ( *I have not uploaded the data folder in the repo due to limited access to the net*). It contains one row for each subject/activity pair and columns for subject, activity, and each feature that was a mean or standard deviation from the original dataset.
