Model Training and Predictions
==============================

Set up the training
-------------------

To allow models to be trained, we will specify which column the models should focus on and set a part of the whole data as training sample.

.. code-block:: console

	y = new_df['TARGET']
	X = new_df.copy().drop(['TARGET'], axis = 1)
	X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.33)

Use of different models 
-----------------------

Model training will use the same pattern : call the model you want to use, fit the data, make the model do predictions and look for its score.

XGBoost
^^^^^^^

.. code-block:: console

	xgboost = xgb.XGBClassifier()
	xgboost.fit(X_train, y_train)
	xgboost_predict = xgboost.predict(X_test)
	metrics.accuracy_score(y_test, xgboost_predict)
	
RandomForest
^^^^^^^^^^^^

.. code-block:: console 

	rf = RandomForestClassifier(n_estimators = 100)
	rf.fit(X_train, y_train)
	rf_predict = rf.predict(X_test)
	metrics.accuracy_score(y_test, rf_predict)
	
GradientBoosting
^^^^^^^^^^^^^^^^

.. code-block:: console

	gb = GradientBoostingClassifier(learning_rate = 0.1)
	gb.fit(X_train, y_train)
	gb_predict = gb.predict(X_test)
	metrics.accuracy_score(y_test, gb_predict)
	
