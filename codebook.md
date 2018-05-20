##The Codebook
###Getting and Cleaning Data Course Project

The purpose of this project is to demonstrate your ability to collect, work with, and clean a data set. The goal is to prepare tidy data that can be used for later analysis. You will be graded by your peers on a series of yes/no questions related to the project. You will be required to submit: 1) a tidy data set as described below, 2) a link to a Github repository with your script for performing the analysis, and 3) a code book that describes the variables, the data, and any transformations or work that you performed to clean up the data called CodeBook.md. You should also include a README.md in the repo with your scripts. This repo explains how all of the scripts work and how they are connected.

One of the most exciting areas in all of data science right now is wearable computing - see for example this article . Companies like Fitbit, Nike, and Jawbone Up are racing to develop the most advanced algorithms to attract new users. The data linked to from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. 

### Information from the original data set

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details.

For each record it is provided:

 1. Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.

 2. Triaxial Angular velocity from the gyroscope.

 3. A 561-feature vector with time and frequency domain variables.

 4. Its activity label.

 5. An identifier of the subject who carried out the experiment.


### Import the files into a large data set

To make the large data set, the data was taken from x_test.txt and x_train.txt, the activity labels were taken from y_test.txt and y_train.txt (and then converted to the text values found in activity_labels.txt), and the subject information was taken from subject_test.txt and subject_train.txt text files. The variables names of each column from x_test.txt and x_train.txt were taken from features.txt. All of this was combined into one data frame.


### Data selection and manipulation for this assignment

After this large data set was constructed, the data involving mean and standard deviation were extracted as discussed.


### Variable names, labels, information from the run_Analysis.R script

features - 561 obs. of 1 variables names for the columns in the x_test and x_train text files

data.all - 10299 obs of 563 variables full data set combination from subject_test, subject_train, y_test, y_train, x_test, and x_train text files all combined. For this program, it is test.data and train.data joined together with rbind.

data.tidy - 180 obs of 68 variables this is the data subsetted to the mean and std variables, after it has been grouped by Subject and Activity and the mean has been calculated for each Subject/Activity with summarise_all, i.e. the final tidy data set.

data.sub - 10299 obs of 68 variables is the data subsetted to the mean /std variables, but prior to the grouping and mean calculations.

subject.test.subject - 2947 obs of 1 variable information read from the subject_test.txt file

subject.train.subject - 7352 obs of 1 variable information read from the subject_train.txt file

test.data - 2947 obs of 563 variables all of the test data (subject.test + y.test + x.test added to each other left to right with cbind)

train.data - 7452 obs of 563 variables all of the train data (subject.train + y.train + x.train added to each other left to right with cbind)

data.test.x - 2947 obs of 561 variables information read from the x_test.txt file

data.train.x - 7352 of 561 variables information read from the x_train.txt file

data.test.y - 2947 obs of 1 variable information read from the y_test.txt file

data.train.y - 7352 obs of 1 variable information read from the y_train.txt file

activity.labels - factor with 6 levels from the activity_labels.txt file. Lists the 6 activities from the data as shown below.

WALKING WALKING_UPSTAIRS WALKING_DOWNSTAIRS SITTING
STANDING LAYING

mean_std.select - 66 values integers indicating the columns to be subset from the full data to select the variables with mean or std.

name.new - 68 values integers that indicate the same colums as subset.a, but also includes the first two columns of the data frame so that subject and activity are selected for the subsetted data set in sub.data