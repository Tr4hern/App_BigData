Last modification date : 21/11/2021
Welcome to the Big Data Applications project by Louis Tardy and Arnaud Pignerol. This project was done as part of our classes.

The work was divided in several folders : data, docs, mlruns, modele and notebooks.

Data : Contains the raw data extracted from Kaggle for the project 
Docs : Contains our sphinx html files. These contain additionnal information and explanations about the project notebooks. The main page is located in docs/build/html/index.html
mlruns : All the mlflow runs are stored here. To look for the results of these runs, you would have to open a terminal, go to the directory of your project and execute "mlflow ui". This will show you a local address where all the runs are saved.
modele : Folder where the models trained in the notebooks are stored
notebooks : Contains the notebooks needed to run the project.
	The notebooks were separated in several parts. To be able to run them without interruption, you would have to do it in the following order :
	- Data Preparation // Extract the data from the csv raw data file, store it locally and start cleaning it
	- Feature Engineering // Select the main features of the data set to keep only them for better model performances
	- Models Training // Train different models : XGBoost, GradientBoosting and RandomForest and store them. Also contains mlflow run commands
	- Predictions // Look again at the models and look for their score / accuracy 
	- Shap // Visual explanations of the data set

