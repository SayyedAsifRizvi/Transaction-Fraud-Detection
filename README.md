# Transaction Fraud Detection


## Background
Recent data from the Federal Trade Commission (FTC) show that consumers lost nearly $8.8 billion to fraud in 2022 ("*New FTC data*," 2023). The FTC received fraud reports from 2.4 million consumers, most of whom were targeted by imposter scams, followed by online shopping scams. These data show that fraudulent transactions impose a massive burden on Americans across the country, so we will create a supervised machine learning model to better predict fraudulent transactions to aid in the process of detecting and stopping scams. To accomplish this goal, we used a dataset from Kaggle that possessed 111,144 credit card transactions that were classified as either fraudulent or not fraudulent (Shenoy, n.d.).For now we are exploring this dataset using python and SQL then and visualizing it using Tableau dashboards

## Data Exploration
The raw dataset from Kaggle contained a random sample of 111,144 credit card purchases. Various features of each credit card purchase were included in the dataset: credit card number, transaction id, gender of card holder, first and last name of card holder, merchant name, transaction category, amount of transaction, geographic information (latitude, longitude, street name, zip code, city, state), date of birth, and time and date of transaction. Using these data, we created two models—a logistic regression and random forest—to predict instances of fraud.

## Data Cleaning
Before creating the models, we had to clean the data so it can be read. First, we exported the data from a csv file to a pandas dataframe. 

![image](https://github.com/nicholaishaw/fraud-detection-project/assets/135463220/f7791125-8fc0-4ab8-af9e-53919e589bae)

**Figure 1.** *Snapshot of the raw dataset.*

Next, we renamed the 'Unamed: 0' to 'transaction_id' and 'amt' to 'amount.' After the columns were renamed, we separated the transaction date and time in the column 'trans_date_trans_time' to two separate columns: transaction date and transaction time.

![image](https://github.com/nicholaishaw/fraud-detection-project/assets/135463220/205a9968-a610-4c0a-af71-f78ca6d00ad4)

**Figure 2.** *Transaction date and time separated.*

After the transaction date and time were separated, we converted date of birth into age using the datetime library.

![image](https://github.com/nicholaishaw/fraud-detection-project/assets/135463220/d88245b9-aeb3-4c3f-aa16-c93e8d623390)

**Figure 3.** *Conversion of date of birth into age.*

Lastly, the columns were reordered, and then we dropped the columns that were not features of the model.

![image](https://github.com/nicholaishaw/fraud-detection-project/assets/135463220/3a69009b-02b4-4295-af80-c6ae3b7f09de)

**Figure 4.** *Columns that were not features of the model were dropped to ensure accuracy of the prediction.*

## SQLite Database
A SQLite database was used to house the clean data. SQLAlchemy was used to connect the clean pandas dataframe to the database. Transaction ID was used as the primary key in the SQLite database.

![image](https://github.com/nicholaishaw/fraud-detection-project/assets/135463220/a796f3c0-f6e0-4d99-b0cf-afba9ea70c6e)

**Figure 5.** *SQLite connection between the pandas dataframe and the database.*





### Model Creation and Model Compiling
upcoming!



## Tableau
To provide further insight issue of fraudulent transactions, we exported our clean dataset of 111,144 to Tableau. Using Tableau, we crafted a series of visuals and interactive dashboards to delve deeper into the complexities surrounding fraud detection.<br>
</br>Access to Tableau Dashboard: [Tableau Dashboard Link](https://public.tableau.com/app/profile/sayyed.asifb.rizvi/viz/fraud-detection-visuals-tableau-workbook/Story)

## References
*New FTC data show consumers reported losing nearly $8.8 billion to scams in 2022*. (2023, February 2023). Federal Trade Commission. Retrieved November 29, 2023, from https://www.ftc.gov/news-events/news/press-releases/2023/02/new-ftc-data-show-consumers-reported-losing-nearly-88-billion-scams-2022

Shenoy, Kartik. (n.d.). *Credit card transactions fraud detection dataset*. Kaggle. https://www.kaggle.com/datasets/kartik2112/fraud-detection?select=fraudTrain
