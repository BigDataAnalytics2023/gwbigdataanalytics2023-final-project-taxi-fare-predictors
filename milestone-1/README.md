# Taxi Fare Predictors
To create predictions, the industry today significantly relies on data analytics. These forecasts result in profitable business strategies that heavily rely on machine learning. 
Before matching a consumer to a driver, popular taxi services like Uber and Lyft give their users an estimate of the cost of the taxi. 
Using the public dataset made available by the NYC Taxi and Limousine Commission (NYC-TLC), we attempt to offer a comparable solution. 
The goal is to do feature engineering on massive amounts of data collected in NYC-TLC's open data repository, train a prediction model utilizing that data, and then deploy that model. 
The crucial concept is to comprehend and put into practice a data analytics pipeline, which serves as the cornerstone of data processing in modern software engineering.
Our system will do its best efforts to process the incoming data from various taxi rides, which will be processed in order of gigabytes. 
Data processing can be further specialized in this case by using a data pipeline to read the data in parallel, performing different data preprocessing tasks simultaneously, such as data cleaning and feature engineering, storing the preprocessed data in-memory for quicker access, and then training a machine learning model on top of it to perform fare prediction. 
The solution that we will build uses various Amazon Web Services. We will pull in records of data from S3 into the EMR cluster where the data would be preprocessed. 
We would also create jobs for EMR to perform feature engineering in parallel. This task would be followed by storing the processed dataset on S3. 
Once this step is completed, we can play around with multiple machine learning models using Sagemaker and try to find the best approach for prediction. 
At the end, we would provide an API to the user for making predictions on demand.
The major tasks here can be broken down into:
1) Efficiently performing read operations on billions of records in parallel stored on S3 in the form of a CSV file.
2) Processing the data in order to make it ready for consumption by the machine learning model. This would involve performing data cleaning, feature engineering etc.
3) Storing the processed dataset to a new bucket which will act as the training set for machine learning models.
4) Training machine learning models and finding out the best prediction system through cross-validation.
5) Creating an API that takes parameters such as start and ending location and time of travel and receive a prediction.

Verification of this data pipeline would depend on the accuracy of the machine learning models as well as the scalability of our data pipeline to large amounts of data. 
