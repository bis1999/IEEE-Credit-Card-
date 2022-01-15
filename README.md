# Credit Card Fraud Classification
https://www.kaggle.com/c/ieee-fraud-detection/overview

## Introduction 
The objective of this Kaggle Competitions is predicting the probability that an online transaction is fraudulent, as denoted by the binary target isFraud.

## Data Description
- TransactionDT: timedelta from a given reference datetime (not an actual timestamp) TransactionDT first value is 86400, which corresponds to the number of seconds in a day (60 * 60 * 24 = 86400) so I think the unit is seconds. Using this, we know the data spans 6 months, as the maximum value is 15811131, which would correspond to day 183.”

- TransactionAMT: transaction payment amount in USD “Some of the transaction amounts have three decimal places to the right of the decimal point. There seems to be a link to three decimal places and a blank addr1 and addr2 field. Is it possible that these are foreign transactions and that, for example, the 75.887 in row 12 is the result of multiplying a foreign currency amount by an exchange rate?”

- ProductCD: product code, the product for each transaction “Product isn't necessary to be a real 'product' (like one item to be added to the shopping cart). It could be any kind of service.”

- card1 - card6: payment card information, such as card type, card category, issue bank, country, etc.

- addr: address “both addresses are for purchaser
  - addr1 as billing region
  - addr2 as billing country”
- dist: distance "distances between (not limited) billing address, mailing address, zip code, IP address, phone area, etc.”
- P_ and (R__) emaildomain: purchaser and recipient email domain “ certain transactions don't need recipient, so R_emaildomain is null.”
- C1-C14: counting, such as how many addresses are found to be associated with the payment card, etc. The actual meaning is masked.

- D1-D15: timedelta, such as days between previous transaction, etc.
- M1-M9: match, such as names on card and address, etc.
- Vxxx: Vesta engineered rich features, including ranking, counting, and other entity relations.




 - DeviceInfo : https://www.kaggle.com/c/ieee-fraud-detection/discussion/101203#583227

 - “id01 to id11 are numerical features for identity, which is collected by Vesta and security partners such as device rating, ip_domain rating, proxy rating, etc. Also it recorded behavioral fingerprint like account login times/failed to login times, how long an account stayed on the page, etc. All of these are not able to elaborate due to security partner T&C. I hope you could get basic meaning of these features, and by mentioning them as numerical/categorical, you won't deal with them inappropriately.”


<br>Afte Exploring the Data, I moved on to creating Boosting Models , following table represents the performance of different models:
```
+---------------+--------------------------+--------------+
|     Model     | Validation roc_auc_score | Kaggle Score |
+---------------+--------------------------+--------------+
| Random Forest |          0.9588          |   0.895851   |
|    LightGBM   |          0.975           |   0.916946   |
|    Adaboost   |          0.8729          |   0.888065   |
|    XGBoost    |          0.9907          |   0.905887   |
+---------------+--------------------------+--------------+
```
At the end I created features after seeing model's feature importance
![alt text](https://github.com/[username]/[reponame]/blob/[branch]/image.jpg?raw=true)




