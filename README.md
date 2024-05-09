# Week 19 Challenge - Crypto Clustering

<img src="Readme Pics/Opening Pic.png" width="1000" height="300">


## Original Data

In this Crypto Clustering, we were tasked to use Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.  This assignment was accomplished by completing a K-Means and PCA analysis and comparing the results for any output differences.  The original data was provided in a .csv file labeled crypto_market_data and was read into a data frame for analysis.  The initial data frame output and line graph representing the data can be seen below.     

<br>
<img src="Readme Pics/Pic 1.png" width="1000" height="300">
<img src="Readme Pics/Pic 2.png" width="800" height="400">
<br>


## Crypto Clustering with K-MEANS

To start the analysis, the data needed to be scaled to ensure that the scale size of the data was consistent throughout the data set.  This task was accomplished by using StandardScaler that is available in the scikit-learn library.  An example of the scaled data can be seen below.   

<br>
<img src="Readme Pics/Pic 3.png" width="1000" height="200">

Next, the best value for K needed to be calculated.  This was accomplished setting up a list of incrementing numbers up to ten and setting an empty list to hold the inertia values.  A for loop was then set up to process through the cluster options, fit the model to the scaled data and append the inertia values to the inertia list.  This data was then entered into a data frame and plotted into an elbow curve to identify the best value for K which ended up being four.    
<br>
<img src="Readme Pics/Pic 4.png" width="700" height="300">

The model was set up using the optimal four clusters, the model was fit to the original scaled data, the model was used to predict the crypto clusters and the information was added to a copy as a new column to the original scaled data frame.  The information was then red into a scatter plot to show the results.  The results examined crypto currency the 24-hour percentage change price to the 7-day percentage.  The results showed a reasonable correlation between clusters 0, 1, and 2, with cluster 3 appearing more volatile with a negative five percent change over a 24-hour period and a zero percent change over the 7-day percentage, placing it far the left of the other clusters.        
<br>
<img src="Readme Pics/Pic 5.png" width="1000" height="200">
<img src="Readme Pics/Pic 6.png" width="700" height="300">
<br>

## Crypto Clustering with PCA 
For the PCA analysis, pca.fit _transform was used on the original scaled data to manipulate it into three principal components.  After checking the variance ratio for the newly aligned data, these three groups were shown to represent 89.5% of the variance of the data set.  Then original crypto currency was then acquired, and the information was placed in a data frame seen below. 

<br>
<br>
<img src="Readme Pics/PCA Pic 1.png" width="400" height="200">


<img src="Readme Pics/PCA Pic 2.png" width="700" height="300">
<img src="Readme Pics/PCA Pic 3.png" width="400" height="200">
<img src="Readme Pics/PCA Pic 4.png" width="700" height="300">





<br>

## Results/Comparison



<br>

<img src="Readme Pics/Compare Pic 1.png" width="1000" height="300">
<img src="Readme Pics/Compare Pic 2.png" width="1000" height="300">



## Conclusion
