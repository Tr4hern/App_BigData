Shap application
================

Creating a TreeExplainer
------------------------

.. code-block:: console

	explainer = shap.TreeExplainer(xgboost)
	shaplayValues = explainer.shap_values(X_test)


Using shap to visualize explanations
------------------------------------

A specific point of the dataframe
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

There are 101479 points in our X_test, in order to visualize the impact of each column on the target, we can make some graphs for a specific point.

In our case, we used a bar plot to visualize these.

.. code-block:: console

	shap.bar_plot(shaplayValues[0], feature_names = X_test.columns, max_display = len(X_test.columns))

.. image:: barplot.png
	:width: 600

We also tried a force plot.

.. code-block:: console

	shap.plots.force(explainer.expected_value, shaplayValues[0], X_test.iloc[0])

.. image:: forceplot.png
	:width: 600


All points of the dataframe
^^^^^^^^^^^^^^^^^^^^^^^^^^^

In order to visualize the impacts of each classes on a single graph, we can do similar commands.
However, there was a problem with some graphs, like the force one. Because of the number of points in X_test, our computers froze while trying to plot.

.. code-block:: console

	shap.plots.bar(explainer(X_test))


.. image:: barplotallpoint.png
	:width: 600



A summary of the dataframe
^^^^^^^^^^^^^^^^^^^^^^^^^^

Finally, we ploted a summary of the impact of each classes in a summary_plot.

.. code-block:: console

	shap.summary_plot(shaplayValues, X_test, plot_size = (15, 10))


.. image:: summary.png
	:width: 600