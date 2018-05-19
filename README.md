# G-C-data-Peer-assignment-week-4
This is solution to 3rd course(Getting &amp; cleaning data)  week 4 assignment of  coursera data science specialization.
------------------------------------------------------------------------------------------------------------------------

You should create one R script called run_analysis.R that does the following.

1. Merges the training and the test sets to create one data set.

Ans:

    a. Read each training data(x, subject & activity) separately and merged into single data frame.

    b. Read each test data(x, subject & activity) separately and merged into single data frame.

    c. Combined test data & and training data into singlle data frame using rbind function.


2. Extracts only the measurements on the mean and standard deviation for each measurement.

Ans: 
    a. added column names to data using features dataset.

    b. Discarded all column names that does not containing mean & standard deviation.



3. Uses descriptive activity names to name the activities in the data set.

Ans:
 
    Map "activity" column with "lables" data set 


4. Appropriately labels the data set with descriptive variable names.

Ans:
 
    Replaced the names in data set with names from activity labels


5.From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

Ans: 

    a. Summarized the output dataset of Question 4 , by grouping them into activity and then subsrouping them into subject.

    b. Calculated the mean of each activity subjectwise.