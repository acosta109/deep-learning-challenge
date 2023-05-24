## Overview of the Analysis
I aim to create a Neural Network model to help select funding applicants for Alphabet Soup. I do this by pulling a CSV file containing more than 34,000 
successful applicants. I clean up the data by removing name and EIN and determining which `APPLICAITON_TYPE`s and `CLASSIFICATIONS`s were put into a new
value  `Other`. I create dummie columns for each non-numerical `affiliation_dummies = pd.get_dummies(application_df['AFFILIATION'])` and then remove all the
extraneous columns `application_df.drop(['AFFILIATION', 'USE_CASE','ORGANIZATION', 'SPECIAL_CONSIDERATIONS', 'INCOME_AMT', 'APPLICATION_TYPE', 'CLASSIFICATION'], axis=1, inplace=True)` I tried many different models to better optimize the results. 

`nn = tf.keras.models.Sequential()`
`nn.add(tf.keras.layers.Dense(units=30, activation=act_sig, input_dim=42))`
`nn.add(tf.keras.layers.Dense(units=15, activation=act_relu))`
`nn.add(tf.keras.layers.Dense(units=1, activation=act_sig))`

Among the different models I tried, I changed the number of nodes, layers, and epochs. I also tried different activation levels at each layer to reach the 
75% accuracy threshold. 

## Results
Most of my models were in the range of 0.726-0.738. We can see the summary and accuracy of the model below.
<img width="526" alt="summary" src="https://github.com/acosta109/deep-learning-challenge/assets/119609975/9c8db002-b258-4cee-abfa-198827f99e65">
<br/>
<img width="414" alt="accuracy" src="https://github.com/acosta109/deep-learning-challenge/assets/119609975/d100e23b-e114-40e4-811c-373c058a3db7">

## Summary

From the results above and description of past models, the Neural Network model is fairly accurate at determining the succcess of applicants for Alphabet 
Soup. As noted above, I struggled to reach the 0.75 threshold for accuracy. I do not strongly recommend this model. In its current state, it is accurate more 
often than not, but in a business setting, I would not recommend this as a long term solution. I would look at further optimizing the existing model or trying
a a different one.

