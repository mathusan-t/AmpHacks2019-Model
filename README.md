# AmpHacks2019-Model
This project consists of the data creation for the hackathon, as well as the code for all models created and evaluated.

## The Problem
Our goal was to pitch an alternative method of financial support for high school students preparing for post-secondary education. The alternative method has been introduced in select colleges in the United States and is called an **Income Share Agreement (ISA)**. A summary of how an ISA works; a student goes through the application process which descrbes a student's details, including name of University/college and expected degree, and investors pool together to finance the student's expenses for their education. Once the student begins working, a portion of their income is directed back to the investors for a fixed number of years.

My job as the Data Scientist of the group (we had one Business Analyst, two Developers, and one Data Scientist) was to generate fake data that reflects student's expected income upon graduation based on their degree, and feed this data into a classification model that would classify a student's expected income to fall within a range. 

Notes on Generating Test Data:
-	Currently only used program name and university
-	Lack of recent data; there was a study from 1970 that was very messy and didn’t feel significant enough to use
-	Assumptions made:
    - Restricted this to full-time students that have gotten into an Ontario university
    - No international students were considered; since we had a weekend to create our prototype, we were more focused on showing functionality of the project than generating the most diverse dataset possible 
    - Generated dataset included 50000 rows with four features that we felt would affect income
      - Program Name (limited to 5)
      - University Name (limited to 6)
-	Projected income was a range, the value that was used in the equation was the midpoint of the range
-	Since our target was categorical, decided to experiment with **k-Nearest Neighbours, Decision Tree, and Random Forest**
    - All gave almost identical accuracy (91%), but kNN gave better precision than the others did for low
    - Still wasn’t great, but that was because of the quality of the generated data
-	With actual data there should be more relevant features and actual income values
-	Income values that were generated were based on Ontario averages for starting salaries for people in those fields, normally distributed with mean (given by paysalary.com) and standard deviation (assumed to be +/- 5000 based on the range of starting salaries )
