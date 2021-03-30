Getting and Cleaning Data Project
==============

This GitHub Repository is created for the 
[Getting and Cleaning Data](https://class.coursera.org/getdata-007) Course Project.

## Project Description ##

The purpose of this project is to demonstrate the ability to collect, work with, and clean a 
data set. 
The goal is to prepare tidy data that can be used for later analysis.  

In more details, the following steps are required to complete the assignment:
    1) a tidy data set as described below;
    2) a link to a Github repository with your script for performing the analysis; 
    3) a Code book that describes the variables, the data, and any transformations performed 
    to clean up the data called.


### Data Set Description

Citation from the UCI Machine Learning Repository:
"The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain."


### Source Data

Data + Description can be found here [UCI Machine Learning Repository](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

## Data Analysis ##

To perform the data analysis it is required to perform the following **steps**:

* **Clone** this repository into a folder on the local machine:
    `git clone https://github.com/beggart/Getting-and-Cleaning-Data-Course-Project.git` 

*  **Set the Working Directory** to the folder where the Git repository has been cloned:

        setwd("<CLONE REPO FOLDER PATH>")
    
* **Source** the `run_analysis.R` script: 

        source("run_analysis.R")

  Sourcing the `run_analysis.R` script will perform the actual analysis. In particular:
     - installs package (reshape2) and loads it as well as data.table
     - Download the dataset to 'dataFiles.zip', unzips to the directory 'UCI HAR Dataset'
     - Read the Dataset
     - Merges the training and the test sets to create one single data set.
     - Extracts only the measurements on the mean and standard deviation for each measurement. 
     - Uses descriptive activity names to name the activities in the data set
     - Appropriately labels the data set with descriptive variable names. 
     - Creates a second, independent tidy data set with the average of each variable 
         for each activity and each subject.

  After performing the analysis, the following files will be created:

    - `tidyData.txt` 
    

* **Use data**: to read and use the data it is necessary to run the following command:

        tidyData <- read.table("tidyData.txt", sep = ",", header = TRUE)

  It will correspond to a `180x68` data frame w/ 30 subjects and 6 activities
  (i.e., 30 x 6 = 180 rows)
