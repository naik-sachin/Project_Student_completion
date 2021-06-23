# Introduction:
According to colleboard, High school graduates typically apply to 5-8 universities. The typical college selection process involves considering factors such as proximity to their residence, scholarship/ expenses, colleges chosen/recommended by their peer’s relatives, their academic performance etc. A lot of students transfer out after their first/second year due to various reasons. These students affect the university in a n egative way in terms of graduation rates, finances etc.Because a lot of the financial resourses are invested in recruiting these students in addition to 1st year scholarship, placement testing, advising etc. The primary goal of this analysis is to help the universities identify students who are more likely to complete their course work and graduate by determining key indicators that will help our marketing team narrow their recruitment effort by creating a better student profile.

# Data
The data did not require any major cleaning or pre-processing.
The data that was used from the Universtiy included a lot of features but the following attributes were used as the rest of it was administrative: 
Gender (M/F)         
Major (47 possible majors)          
Housing status(resident/commuter)        
SAT             
ACT          
HSGPA (scale of 4)          
AddrLine1       
City            
State           
Zip
To be in compliance with the universities data privcay policy, the data is not shared in this analysis since its on a public platform.
## Processing the data : 
The data was processed in the notebook labelled Preprocessing.
Students majors were categorized as STEM , Commerce , Humaniteis/Arts . The idea behind this categorization is as follows :Most students in these categories take the same course work for the first 2-3 semesters  so it does not impact our analysis .
Some student shared multiple reported SAT and High school GPA (HSGPA). In such chases the highest reported scores were used.
Median household income data was obtained from census.gov based on student zipcode.
SPSERV represents students in a special program. Such programs are often aided by the government or external agencies.
Distance from the univeersity to students zipcode was calculated based on pgeocode which is a library for US zipcode distance. More infomration can be found at https://pypi.org/project/pgeocode/.
Zip_count was a engineered feature that represents the number of applicants from the same zipcode. This number represents word of mouth metric , as applicants are more likely to attend universities where they know a former graduate via friends/family or word of mouth advertisement etc. 
Rest of the data is either student reported or generated by the university. 

# Visuals 
The EDA is in the notebook labelled EDA and modelling.
Initial EDA and visuals focused mainly on completion rates based on various categorical variables. 
![alt text](https://github.com/snaik21352/Student_completion/blob/main/Completion_rates.png)
The aid of these visuals were used to come up with a student profile that is a statistically valid representation of our students.


# Modelling 
The Modelling is in the notebook labelled EDA and modelling.

![alt text](https://github.com/snaik21352/Student_completion/blob/main/Confusion_matrix.png)


Students who completed were classified based on a Decision tree classifier and a  random forest classifier with repeated  cross validation , recursive feature elimination and resampled data to obtain nearly 90% prediction accuracy. 

# Future Work 
We can use student highschool course work /grades to assess students prepradness for college which directly impacts completion rate.
I would like to use Student's college GPA on a semester basis with semesters after which a student drops out to determine drop out risk rates.
I would also like to identify key zipcodes to recruit students using some form of clustering method.
