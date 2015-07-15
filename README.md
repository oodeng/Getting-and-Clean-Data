# Getting and cleaning data

For creating a tidy data set of wearable computing data originally from http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

## Files in this repo
* README.md -- explanation
* CodeBook.md -- codebook describing variables, the data and transformations
* run_analysis.R -- actual R code

## run_analysis.R goals
Please create one R script called run_analysis.R that does the following:
1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive activity names. 
5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject. 

Then run in a folder of the Samsung data (the zip had this folder: UCI HAR Dataset)
Bear in mind script assumes it has in it's working directory the following files and folders:
* activity_labels.txt
* features.txt
* test/
* train/

Following is the  output is created in working directory with the name of output.txt

*Note:* the R script is built to run without including any libraries for the purpose of this course.

## run_analysis.R walkthrough
It follows the goals step by step.

* Step 1:
  * read all the data
  * put it together in the format of: subjects, labels, everything else

* Step 2:
  * read the features
  * only retain features of mean and standard deviation
  * select only the means and standard deviations from data
  * increment by 2 because data has subjects and labels in the beginning

* Step 3:
  * read the labels (activities)
  * replace labels in data with label names

* Step 4:
  * first make a list of the current column names and feature names
  * then tidy that list
  * by removing every non-alphabetic character and converting to lowercase
  
* Step 5:
  * find the mean for each combination of subject and label
  
* Final step:
  * Write the new tidy set into a text file called data_set_with_the_averages.txt, formatted similarly to the original files.
