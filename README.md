# Judging-Pre-owned-bicycle-Deals-Type-Using-Machine-Learning-Methods

Under the influence brought by Covid-19, people who used to take bus for commuting and traveling are tending to cycle to the places they would like to go. So many of them choose to buy a pre-owned bike because of the cheap price. However, many of them complaint that they didn’t get the lowest price they could get. The focus of this study is using logistic regression to build a classifier to determine if a pre-owned road bicycle deal is a good deal or not. Unlike new prod- ucts with a fixed price, asymmetric information between the sellers and buyers before the transaction, lack of reliable transactional schemes due to frequent frauds and chaos during the transactions, and missing after-sales guarantee mechanism in pre-owned things deals. The result of the study could help people intending to buy a pre-owned road bicycle before they make the deal by letting them enter the key information of the bicycle they are about to buy and predict if the deal is a good deal or not, where "0" represent the bad deal while "1" represents the opposite.

## KeyWords
- Machine learning
- Logistic regression
- Bicycle

## Table Of Contents
- Background
  - About Author
  - About Market Environment
- Define the Influence Factor
- Data Pre-processing
- Machine Learning Model
  - Logistic Regression
  - K-Fold
- Problems and Future Outlook
- ACKNOWLEDGMENTS

## Background
- Liyourong Wang
  - The author has been in love with cycling sport since the day he put his foot on the peddle, being a pro-cyclist to race in Tour de France has been his days and dreams
  - During the Covid-19 time, the author spotted the market demand towards bicycles, so he started his pre-owned bike dealer career, at the mean time, the author was amazed by the power of machine learning from his "Credit Card Fraud" project. SO he developed a pre-owned bike deal classifier to help him 
- Demographical Background
  - Governments propose maintaining a social distance between people for safety concerns, making taking public transportations like metros and buses for people to be unlikely. Comsumers need a bike to commute.
  - A normal consumer would have trouble distinguishing the value of the bicycle and then buying a bicycle at a higher price
  
  ## Define the Influence Factor
  <img width="823" alt="截屏2023-03-29 04 40 43" src="https://user-images.githubusercontent.com/105031962/228477368-8a053035-353b-48f3-9f68-82da2c00b038.png">
  
After conducting a survey towards the consumers, the author set Age, Transmission Kit, Frame Material, Brand and Price as the input of the classifier. To testify the survey result, I introduced Caring Factor(CF) to quantify the survey data, in order to generate a legit data set to analyze:

<img width="372" alt="截屏2023-03-29 15 18 46" src="https://user-images.githubusercontent.com/105031962/228645005-3fac0483-25fc-48a7-b208-340392559eac.png">


  ## Data Pre-processing
  <img width="1057" alt="截屏2023-03-29 15 14 36" src="https://user-images.githubusercontent.com/105031962/228644070-fa88400e-1d81-4872-a771-c91832de4974.png">
  
  This table is the original data example collected from local bike shops. As you may notice, the raw data is different in unit, dimention, language... To rule out the impact brought by the difference in the number of digits, some adjustments are about to be made to make the model more general to the public.
  I assigned numbers towards different kinds of Frame Materials and Transmission Kit, and substract all the bike ages to a single digit number， lowering the Multicollinearity of the raw data. After a series of normalization the final data to present looks like below:
  <img width="1056" alt="截屏2023-03-29 15 23 56" src="https://user-images.githubusercontent.com/105031962/228646089-6cd282ff-0fed-4bc9-8b2d-df087a427eea.png">
  
## Machine Learning Model
The author build this model from Logistic Regression, and enhanced the usage of data using K-Fold:
# Logistic Regression
<img width="703" alt="截屏2023-03-29 15 24 56" src="https://user-images.githubusercontent.com/105031962/228646285-877d0b8d-a1e5-4793-871a-4ddca683c205.png">

This is a diagram showing how the logistic regression model looks like, the way it calculates are more or less derived from the equation below:

<img width="507" alt="截屏2023-03-29 15 31 22" src="https://user-images.githubusercontent.com/105031962/228647699-e0eaada6-a195-44d3-83e3-7fc913878c03.png">

### K-Fold

"The K-fold cross-validation process then involves using K-1 folds as the training set to train the model, while the remaining fold is used as the validation set to evaluate the model's performance. This process is repeated K times, with each fold being used as the validation set exactly once."

In this classifier, the author encountered huge difficulties developing an accurate data due to the lack of data. Therefore the K-Fold cross-validation process is used to improve the data usage efficiency

## Problems and Future Outlook
This model is still improving in its accuracy. The model now is encountering some difficulties due to several reasons:

### Location 
The data collected only from Zibo may not be representative of larger cities like Beijing or Shanghai, where operational costs are higher. Thus, a selling price considered reasonable in Zibo may not be reasonable in larger cities. To improve model accuracy, the location of the bike shop should also be considered in determining the "good deal price" interval, particularly for shops in larger cities where operational costs are higher.

### Transmission Kit
Due to limited data, the classifier cannot be applied to bicycles with electric transmission kits such as Shimano Ultegra di2, Dual-Ace di2 or Sram E-Tap.
Upgrades in transmission kits make it difficult to accurately determine the generation and performance of a bicycle's transmission kit based solely on its name in the dataset.
The pre-processing of the data only includes Shimano transmission kits, as there is not enough data on other brands such as SRAM, Campagnolo, and Microshift in the dataset.

### Individual Preference
Individual preferences for specific transmission kits or frame materials have not been considered in the model due to limited data and the desire to create a classifier applicable to as many people as possible. Some members of HDCA prefer a 105 R7000 transmission kit over a Dual-Ace R9100 kit to save money for upgrades to wheels and frames. Similarly, some people prefer high-performance aluminum frames over low-performance carbon fiber frames, which can affect the actual "Good Deal Price Interval." While these preferences exist, they have not been taken into account in the model's development.

## ACKNOWLEDGMENTS
Firstly, I would like to express my greatest gratitude to Professor Rekesh Kumar who taught me a lot in Machine learning method, he’s the person who lead me in the world of Machine learning. Also, Wu Jiatong is the TA in Dr. Kumar’s class, he taught me about math and statistic knowledge that’s needed for developing the model. In preparation for data. I would express my thanks towards cycling origanization and cyclists who contributed to my data collecting work. Thanks to Jiaqiong Wu, who gave me practical advice in revising my article along the way. And finally, I would express my gratitude to Mr. Junjun Li who offered me so much help in the problems and questions I encountered in developing the model, he gave me insightful instructions and supported me all the time.

