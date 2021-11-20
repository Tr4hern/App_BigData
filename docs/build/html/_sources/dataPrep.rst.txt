Data Preparation and Feature Engineering
========================================

Data set
--------

The data set used for this project can be downloaded `here <https://www.kaggle.com/c/home-credit-default-risk/data>`_.

The goal with it when you download if from the page is to try and predict how an applicant is capable of repaying a loan.

Data Preparation
----------------

The goal of this part is to keep only the data that will be relevant for our model. A good way to set this up is to look for missing values using missingno library:

.. py:function:: missingno.bar(DataFrame)

	Return a graph displaying missing values for any column of your dataframe
	
	:param DataFrame: The DataFrame you need to study on 
	:return: The graph showing missing values
	:rtype: AxesSubPlot

Feature Engineering
-------------------

Our goal afterwards is to check the correlation between each column of the dataFrame and the target to keep only main features. A way to do it is to use the following DataFrame function: 

.. py:function:: DataFrame.corr(method='pearson', min_periods=1)

	Returns a DataFrame in form to be used as a correlation matrix.
	
	:param method: Used method of correlation (default is pearson).
	:type method: {'pearson','kendall','spearman'} pearson : standard correlation coefficient - kendall : Kendall Tau correlation coefficient - spearman : Spearman rank correlation
	:param min_periods: Minimum number of observations required per pair of columns to have a valid result. Only available for Pearson and Spearman correlation.
	:type min_periods: Is Optional, int.
	:return: Correlation matrix
	:rtype: DataFrame
	
By keeping only the values above 5%, we make sure that we keep only the data that represents the best the original data to help train our model.
