# West_Nile_Virus_Chicago
Group project, EDA, Classification models

---

## Group/Contributers
* Youn Hee Pernling Frödin
* Tucker Allen: https://github.com/Tucker-Allen
* Andrew Carl: https://github.com/Andrew-Carl
* David Hoffman: https://github.com/davehoff


---

## Description
Welcome to your first week of work at the Disease And Treatment Agency, division of Societal Cures In Epidemiology and New Creative Engineering (DATA-SCIENCE). Time to get to work!

Due to the recent epidemic of West Nile Virus in the Windy City, we've had the Department of Public Health set up a surveillance and control system. We're hoping it will let us learn something from the mosquito population as we collect data over time. Pesticides are a necessary evil in the fight for public health and safety, not to mention expensive! We need to derive an effective plan to deploy pesticides throughout the city, and that is exactly where you come in!


---

## Task
Where will the West Nile virus be present in Chicago?


#### Goals
* Work as a group
*
* Performe EDA
* Run at least one model
* Submit code at Kaggle 



---

## The Data

Can be found here: https://www.kaggle.com/c/predict-west-nile-virus/

### INFO about about the data
Spray data - Years: 2011, 2013
Weather data - Years: 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014
Training data - Year: 2007, 2009, 2011, 2013
Test data - Year: 2008, 2010, 2012, 2014

### What data to use
Since we only have spray data for the training years (odd years) and not the test years (even years) we have 
decided that we are not going to use the spray data. 

We choose to remove station 2 from the weather data.

We also divided the weather data into 2 data frames, odd and even years. This is to make it easier to merge the weather data into the test and training data. 


### Info about the cleaned CSV files
Weather 
- Datetime format is not kept when you turn the data into a CSV and then read the CSV. So you need to do it again when you read in the CSV-file.
- The column named Unnamed: 24 acually do not have a name, it was just empty in the CodeSum column when the dummies were greated.
- Drop column CodeSum. You do not want to use CodeSum and dummies together. (was not done in the cleaning process)
- Change Sunrise and Sunset if they are going to be used. They are strings of time right now, like '0415'. (was not done in the cleaning process)

Spray 
- Datetime format is not kept when you turn the data into a CSV and then read the CSV. So you need to do it again when you read in the CSV-file.

Train/Test
- The following features have been dropped in X_train_clean.csv and X_test_clean.csv. Let me know if you'd like any of them reincorporated for any reason.
	- Date: Information recreated in features 'Year_x', 'Month_x' and 'Day_x'
	- Address: Information recreated in 'Latitude', 'Longitude' and 1-hot encoded zip codes
	- Species: Information recreated in 1-hot encoded species
	- Street: Duplicate information of Address
	- AddressNumberAndStreet: Duplicate information of Address
	- AddressAccuracy: Erroneous information from geocoder
	- Zipcode: Information recreated in 1-hot encoded zipcodes

- The following features have been dropped in weather_odd.csv and weather_even.csv.
	- CodeSum: Information recreated i 1-hot encoded weather features
	- Year_y: Duplicate information from X_train/X_test
	- Month_y: Duplicate information from X_train/X_test
	- Day_y: Duplicate information from X_train/X_test
	- Unnamed: 24: Erroneous information


---

`X_test_clean_v2` and `X_test_clean_v2` have additional features over `v1`, which include:
	- One-hot encoded 'Trap' features


---

## Classification Models
* Logistic regression
* Random Forest
* kNN


---

## Presentation (pdf) and Jupyter Notebook available in repo
