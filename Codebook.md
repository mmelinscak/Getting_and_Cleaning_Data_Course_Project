# Descrition of the script

The script `run_analysis.R`performs five steps as it is described in the course project's definition:

* All the similar data (having the same number of columns and referring to the same entities) is merged (using the `rbind()` function)
* Columns with the mean and standard deviation measures are extracted from dataset and given the correct names (taken from `features.txt`).
* As activity data is addressed with values 1:6, we take the activity names and IDs from `activity_labels.txt` and they are substituted in the dataset.
* Columns with vague column names are corrected.
* A new dataset is generated with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called `tidy_data_set.txt`(uploaded to this repository).

# Variables

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files
* `x_data`, `y_data` and `subject_data` merge the previous datasets for the purpose of further analysis
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_and_std_features` (a numeric vector used to extract the desired data)
* A similar approach is taken with activity names through the `activities` variable
* `all_data` merges `x_data`, `y_data` and `subject_data` in one dataset
* `tidy_data_set` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()` and ease the development.
