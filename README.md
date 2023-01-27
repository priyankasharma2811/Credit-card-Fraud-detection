 Credit-card-Fraud-detection

Credit card fraud detection is major problem faced by all banks and financial organizations. We are trying to build an efficient and fast ML model that can help these institutions to identify patterns and prevent fraud transactions.

Frauds can be committed by fraudsters in various ways:-
1.	Stealing the credit card physically.
2.	Stealing the credit cards holder’s account via deceptive text messages.
3.	Committing card does not present i.e. processing the transactions without physical card it can be done via phone or email.
4.	Making fraudulent copies of credit card by skimming card while swiping.

Challenges associated with the credit card fraud detection are:-
1.	Data availability i.e. as most of the data is private and we are not able to make much link of the features with target variable.
2.	Imbalanced data , as majority of the transactions processed are genuine and only few of them are fraudulent so it is quite difficult to catch those fraud transactions.
3.	Large number of transactions are processed everyday thus our model should be fast enough to process all of them and detect fraud ones.
4.	Fraudsters use hacking techniques against ML models.


How to tackle these challenges:-
1.	We can choose reliable source to collect dataset .
2.	There are many techniques by which we can handle the problem of imbalanced data which will be discussed further.
3.	The model built should be fast and efficient to tackle large number of transactions.
4.	The model should be simple so that if it will get hacked, we can tweak some changes immediately.


Accuracy metrics to evaluate the classification models:-

1.Recall :  The ability of model to find all the relevant cases in dataset . The number of true positive divided by true positive and false negatives.
Cases like credit card fraud detection we want to avoid false negative cases as fraud transaction costs companies a lot . False negative case is when fraud positive transaction is considered as genuine which is more important as compared to false positive means if the genuine transaction considered as fraud.  

2.Precision: The fraction of relevant instances among the retrieved instances. . The number of true positive divided by true positive and false positives.
In the case of credit card fraud detection we precision should also be taken care according to perspective of customers as we can’t classify more genuine transaction as fraud ones

3.F1 Score: It is harmonic mean of both precision and recall if the F1 score is high means our model is doing well. 

4.Accuracy: In case like where the classes are very imbalanced the accuracy is not a good measure to evaluate the performance of our model . As in the random case also it will classify the majority class correct which will eventually give good accuracy. But our major concern is here to detect fraudulent ones which is minority class.

5.Mathew correlation Coefficient: It is a machine learning measure which is used to check the balance of the binary (two-class) classifiers. It considers all the true and false values of confusion matrix that is why it is generally regarded as a balanced measure which can be used even if the classes are very imbalanced.
MCC is high if the model is doing well on both the classes


Various techniques to handle imbalanced data:-

1.Smote (Synthetic Minority Oversampling Technique)
Smote synthesize elements for the minority class. Decide number of k nearest neighbours, drawing lines between the examples in the minority class and any of its b=neighbours  and draw a new sample point along that line. Do until data is balanced.

	Advantages:
	i.	No loss of information.
	ii.	Simple to implement.

	Disadvantages:
	Creating samples of minority class may results in overfitting.

2.Undersampling using tomek links : It starts by finding samples of data from majority class that has lowest Euclidean distance with the minority class data and then remove it . Increases the class separation  and reduce the number of majority class samples along the boundary of majority cluster.

	Disadvantages:
	Loss of information cannot make complete use of existing information.

3. Smote + Tomek:
First smote is implemented to create new synthetic minority class samples to get balanced data. Then Tomek links is used to remove the samples close to the boundary of the two classes to increase the separation between two classes.

4. Balanced Bagging Classifier : Bagging method works by building multiple estimators on different randomly selected subset of a data. Here, our data is imbalanced so we are using balanced bagging classifier .It allows resampling of each subset before training each estimator of the ensemble.


