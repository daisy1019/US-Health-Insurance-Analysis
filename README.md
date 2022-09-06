# US-Health-Insurance-Analysis


**Statement of Goals**

This report is aiming to predict the US health insurance premium charges for people / families, and to find answers to the following questions:

* What are the premium charges based on the given data points? (predicting the charges)

* What are the main factors that affect insurance premium charges? (the relationship between factors)

* What other factors that insurance companies need to take into consideration for giving insurance premiums?


**Description and Location of the Data**

_**Location**_ - this dataset is obtained from kaggle.com and saved into Jupiter notebook for analysis purpose. 

_**Description**_ - this dataset contains 1338 observations x 7 attributes with no missing data, below are the attributes that are included in the dataset. 

* age - age of primary beneficiary
* sex - insurance contractor gender, 0=female, 1=male
* bmi - body mass index, ideally between 18.5 to 24.9
* children - number of children covered by health insurance
* smoker - 0=non smoker, 1=smoker
* region - the beneficiary’s residential area in the US, 0=northeast , 1=northwest, 2=southeast, 3=southwest
* charges - individual medical costs billed by health insurance company


**Exploratory Data Analysis**

_**Number of customer per each category**_

Below tables and graphs show the number counts of sex / smoker / region. 
* Sex - only 14 males than females in the dataset
* Smoker / non-smoker - majority of customers are non smoker, with only 274 customers are smoker
* Region - NE: northwest, NW: northwest, SE: southeast, SW:southwest
  The number of customers are quite evenly distributed from each region, with slight more customers from southeast.
            
!<img width="758" alt="Screen Shot 2022-09-05 at 8 12 22 PM" src="https://user-images.githubusercontent.com/80385435/188539299-d746f128-fa6e-43c3-9d11-8773a4616a98.png">    
      

_**_Relationship between charges and sex / children / smoker / region**_

1). Relationship between charges & sex
 
Males are charged slightly more than females

<img width="278" alt="image" src="https://user-images.githubusercontent.com/80385435/188539510-7687053c-1409-4cb9-8588-8b487b5605db.png">

2). Relationship between charges,  sex and no. of children
Customer with 5 children have the lowest charges, with 3 children have the highest charges.

<img width="272" alt="image" src="https://user-images.githubusercontent.com/80385435/188539529-ba59bf72-f659-4f74-bb2a-c8dafe02e946.png">

3). Relationship between charges, sex and smoker / non-smoker
Customers who smoke are charged much higher than people who don’t smoke

<img width="268" alt="image" src="https://user-images.githubusercontent.com/80385435/188539543-692b472b-072d-4556-8a19-591c0a24258d.png">

4). Relationship between charges and region
Customers from Southeast are charged slightly higher than other customers

<img width="283" alt="image" src="https://user-images.githubusercontent.com/80385435/188539574-de0acff1-cb1f-471b-8f4c-037be91a416c.png">



_**Relationship between charges and age /bmi**_

1). Relationship between charges and age
All ages were divided into 3 categories:
 a) Age <30,           b) age >=30 and <45,           c) age >=45

The graph shows that younger people have lower charges while people are over 45 are charged more.

<img width="244" alt="image" src="https://user-images.githubusercontent.com/80385435/188539705-063992f9-c479-4ef1-8e9b-cc38b84d545d.png">

Below graph illustrates the charges with age and region, older customers are charged more regardless of which region they are from. 

<img width="244" alt="image" src="https://user-images.githubusercontent.com/80385435/188539747-1a889e08-7ad2-4c0a-afa3-c9592cf7d3ad.png">


2). Relationship between charges and bmi
All bmi were also grouped into 3 categories:
 a) Age <30,           b) age >=30 and <42,           c) age >=42

Customers have higher bmi are charged higher as well

<img width="246" alt="image" src="https://user-images.githubusercontent.com/80385435/188539784-63e30827-a4a5-43cd-babc-836b8ee0145d.png">


3). Relationship between charges / bmi / region

Customers are from Southeast who have higher bmi are charged higher respectively

<img width="260" alt="image" src="https://user-images.githubusercontent.com/80385435/188539817-b87b5565-96d9-4b03-a0cd-8ad510f7dced.png">


**Feature Importance**

The following displays the feature importance of this dataset, smoker is the most important feature, then bmi comes second, the third important feature is age, number of children and region are not as important as other attributes. 

The correlation heat map also shows that smoker is the most condition towards charges, with bmi and age come after smoker. 


Feature Importance 

<img width="240" alt="image" src="https://user-images.githubusercontent.com/80385435/188539882-f2fa558e-ca4d-4f63-b8c2-c9cf0c2468dc.png">


Correlation

<img width="222" alt="image" src="https://user-images.githubusercontent.com/80385435/188539896-029c18a2-424f-4dfd-aac9-8bf453e408be.png">


**Model Training and Selection**

Below table represents the training models that were tested and the scores obtained. Gradient Boosting Regressor reached the best score 0.976045424932751 (highlighted in blue), therefore this model is selected for final prediction for insurance charges.



Model Training and Selection

Below table represents the training models that were tested and the scores obtained. Gradient Boosting Regressor reached the best score 0.976045424932751 (highlighted in blue), therefore this model is selected for final prediction for insurance charges.

<img width="503" alt="image" src="https://user-images.githubusercontent.com/80385435/188540027-1093a3c0-3737-40f6-b8ac-23097c2e23f7.png">


**Prediction**

Below is a snap shot of figures between charges and prediction includes the first and last 5 rows from the dataset, the predicted values are not too far from the original values (charges).

![image](https://user-images.githubusercontent.com/80385435/188540135-9100a177-3b5c-4f05-aefd-cb814da87f2e.png)


The following graphs also showing that the predicted values are quite close to the original dataset value. 

The green and red lines from the graph on the left are mostly overlapping with each other, with only a few green lines that are sticking out. 

The cyan dots from the graph on the right have a up trending direction with only a few dots that are outside the straight line.

![image](https://user-images.githubusercontent.com/80385435/188540337-75b0a8af-ba21-47a9-bfe6-f48224af0d0f.png)

<img width="229" alt="image" src="https://user-images.githubusercontent.com/80385435/188540359-2c0c3962-c1b3-4d7b-a218-d6f7fe08e744.png">


**Conclusion**

This analysis shows that people who are healthy and younger tend to be charged less for health insurance, for families with more children that would benefit more from this insurance coverage. 

There are also other factors that could affect the health insurance cost:

* Past Medical History -  people who have severe and chronic medical issues in the past could affect current health insurance charge significantly.

* Occupation - people who work in dangerous site could also face higher insurance premium cost such as people who work in the filed.

* Insurance Coverage Period - a longer coverage period usually costs less than a shorter period.


            
