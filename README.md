CS539 Machine Learning Project
===
Topic: Heart Disease Prediction Based On Machine Learning
===

Group Member: Yuxiao Peng, Zhaohui Li, Longsheng Xie
---
Data:
---
https://www.kaggle.com/ronitf/heart-disease-uci


1.Introduction:
---
Heart disease describes a range of conditions that affect your heart. Diseases under the heart disease umbrella include blood vessel diseases, such as coronary artery disease, heart rhythm problems and heart defects you are born with, among others. The term “heart disease” is often used interchangeably with the term “cardiovascular disease”. Cardiovascular disease generally refers to conditions that involve narrowed or blocked blood vessels that can lead to a heart attack, chest pain or stroke. Other heart conditions, such as those that affect your heart’s muscle, valves or rhythm, also are considered forms of heart disease.

Heart disease is one of the biggest causes for morbidity and mortality among the population of the world. Prediction of cardiovascular disease is regarded as one of the most important subjects in the section of clinical data analysis. The amount of data in the healthcare industry is huge. This data is not always made use to the full extent and is often underutilized. Using this huge amount of data, a disease can be detected, predicted or even cured. This makes heart disease a major concern to be dealt with. But it is difficult to identify heart disease because of several contributory risk factors such as diabetes, high blood pressure, high cholesterol, abnormal pulse rate and many other factors. Due to such constraint’s scientists have turned towards modern approaches like Data Mining and Machine Learning for predicting the disease.

Machine learning has been shown to be effective in assisting in making decisions and predictions from the large quantity of data produced by the healthcare industry. we try to concentrate on heart disease prediction. Using machine learning techniques, the heart disease can be predicted. The medical data such as Blood pressure, hypertension, diabetes, cigarette smoked per day and so on is taken as input and then these features are modelled for prediction. This model can then be used to predict future medical data. The algorithms like K-nearest neighbor, Naïve Bayes, support vector machine and decision tree are used. The accuracy of the model using each of the algorithms is calculated. Then the one with a good accuracy is taken as the model for predicting the heart disease.

2.Data Scanning:
---
1. Age: displays the age of the individual.
2. Sex: displays the gender of the individual using the following format:
    * 1 = male
    * 0 = female
3. Chest-pain type: displays the type of chest-pain experienced by the individual using the following format:
    * 1 = typical angina
    * 2 = atypical angina
    * 3 = non -- anginal pain
    * 4 = asymptotic
4. Resting Blood Pressure: displays the resting blood pressure value of an individual in mmHg
5. Serum Cholesterol: displays the serum cholesterol in mg/dl
6. Fasting Blood Sugar: compares the fasting blood sugar value of an individual with 120mg/dl.
    * If fasting blood sugar > 120mg/dl then: 1 (true)
    * else: 0 (false)
7. Resting ECG: displays resting electrocardiographic results:
    * 0 = normal
    * 1 = having ST-T wave abnormality
    * 2 = left ventricular hypertrophy
8. Max heart rate achieved: displays the max heart rate achieved by an individual.
9. Exercise induced angina:
    * 1 = yes
    * 0 = no
10. ST depression induced by exercise relative to rest: displays the value which is integer or float.
11. Peak exercise ST segment:
    * 1 = upsloping
    * 2 = flat
    * 3 = downsloping
12. Number of major vessels (0–3) colored by flourosopy: displays the value as integer or float.
13. Thal: displays the thalassemia:
    * 3 = normal
    * 6 = fixed defect
    * 7 = reversible defect
14. Diagnosis of heart disease: Displays whether the individual is suffering from heart disease or not:
    * 0 = absence
    * 1, 2, 3, 4 = present

We made some plots to analyze the data:

![image](image/001.png)  
The proportion of heart dicease in data

![image](image/002.png)  
The sex ratio in data, the proportion of female is higher than male.

![image](image/003.png)  
The heart disease frequency for different ages, high probability of heart disease at age 50 to 60

![image](image/004.png)  
The heart disease frequency for different sex, high probability of heart disease in female

![image](image/005.png)  
The age and maximum heart rate

![image](image/006.png)  
The heart disease frequency for ST segment, high probability of heart disease if the exercise ST segment is downsloping

![image](image/007.png)  
The heart disease frequency according to FBS, high probability of heart disease if the FBS is more than 120 mg/dl

![image](image/008.png)  
The heart disease frequency acccording to chest pain type, the anginal pain and atypical angina have the high probability of heart disease

3.Data Processing:
---
![image](image/009.png)

Then we used PCA and try to visualize it with 2 classes.

From the result, we can tell that the classification is not very clear when using two features. We can know that the factors that affect heart disease are not simply determined by two features, but there are many conditions before they can be classified.

![image](image/010.png)

We also use TSNE and visualize it with 2 classes.

4.Model Selection:
---
Using k-fold = 10 cross-validation to choose best ML algorithm, we run the model 10x with 70/20 split intentionally leaving out 10% of the data:

![image](image/011.png)

So we can see logitic regression method has the highest accuracy score among the all algorithm

5.Model Evaluation:
---
We choose logistic regression and made 2 confusion matrix for each train data and test data, the accuracy for train data is 86.0% and for test data is 91.8%

![image](image/012.png)
![image](image/013.png)

The ROC curve of the model with the AUC is 0.942

![image](image/014.png)

6.Future work:
---
Heart Disease is one of the major concerns for our life. It is difficult to manually determine the odds of getting heart disease based on risk factors. However, machine learning techniques are useful to predict the output from existing data. We selected the model that is most suitable for predict the heart disease. Using logistic regression to assist the doctor to judge if a patient have heart disease using its probability. For our future work, we hope we can make a program. When the patient input his or her sympols, then he or she can get a probability of heart disease. Because the performance of heart disease is very complicated, I hope to find other clinical data to train our model and increase our accuracy.
