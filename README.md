# Week 19 Challenge - Crypto Clustering

<img src="Readme Pics/Opening Pic.png" width="1000" height="300">


## Original Data

In the Crypto Clustering Challenge, we were tasked to use Unsupervised Learning Models to predict how cryptocurrencies will be affected by 24-hour or 7-day price changes.  This was accomplished by completing a K-Means and PCA analysis and comparing the results.  The original data was provided in a .csv file labeled crypto_market_data and was imported to a data frame for analysis.  The initial data frame output and line graph representing the data can be seen below.     

<br>
<img src="Readme Pics/Pic 1.png" width="1502" height="324">
<img src="Readme Pics/Pic 2.png" width="671" height="336">
<br>


## Crypto Clustering with K-MEANS

To start the analysis, the data needed to be scaled to ensure consistency throughout the data set.  This was accomplished by using StandardScaler which is available in the scikit-learn library.  An example of the scaled data can be seen below.   

<br>
<img src="Readme Pics/Pic 3.png" width="1481" height="185">

Next, the best value for K needed to be calculated.  This was accomplished setting up a list of incrementing numbers and creating an empty list to hold the inertia values.  A for-loop was set up to process through the cluster options, fit the model to the scaled data, and store the inertia values.  The data was entered into a data frame and plotted to an elbow curve to identify the best value for K.  The results identified the optimal value to K to be four.    
<br>
<img src="Readme Pics/Pic 4.png" width="584" height="252">

A model instance was initiated using the optimal four clusters, fit to the original scaled data, and run to predict the crypto clusters.  Finally, the predicted clusters were added to the data frame and a scatter plot was used to view the results.  The results showed a reasonable correlation between clusters zero (blue), one (red) and two (gold), with cluster three (green) located far the left of the main cluster.        
<br>
<img src="Readme Pics/Pic 5.png" width="1594" height="205">
<img src="Readme Pics/Pic 6.png" width="585" height="252">
<br>

## Crypto Clustering with PCA 
For the PCA analysis, pca.fit _transform was used on the original scaled data to manipulate it into three principal components.  After checking the variance ratio for the newly aligned data, these three groups were shown to represent 89.49% of the variance of the data set with a 10.5% variance loss.

<br>
<img src="Readme Pics/PCA Pic 1.png" width="385" height="114">
<img src="Readme Pics/PCA Pic 7.png" width="327" height="40">


To identify the best value for K for the PCA data, an integer list and an empty list to hold inertia values was created, a for-loop was used to cycle through the PCA data, fit to the model to the scaled data, and store the inertia values. This data was then plotted to an elbow curve to identify the best value for K.  The ideal value for K was again identified as four.

<br>
<img src="Readme Pics/PCA Pic 2.png" width="581" height="248">


The cluster results were added to the PCA data frame and it was used to produce a scatter plot below.  In the PCA scatter plot cluster two (gold) and cluster zero (blue) are producing similar results while cluster one (red) and three (green) have been relocated far to the right side of the main cluster. 

<br>
<img src="Readme Pics/PCA Pic 3.png" width="436" height="186">
<img src="Readme Pics/PCA Pic 4.png" width="582" height="247">

<br>


## Results/Comparison

When examining the two elbow curves, the results share similar characteristics with both graphs identifying the optimal number for K as four.    

<br>

<img src="Readme Pics/Compare Pic 1.png" width="1166" height="249">


The two scatter plots produced mixed results showing commonalities and exposing some differences.  In both scatter plot images, cluster two (gold) and cluster zero (blue) comprise the main cluster and show similar results between the two plots.  Both main clusters maintained a consistent range on the X and Y axis, and both produced a small amount of overlap between the two clusters.  The main difference between the two scatterplots can be seen with the relocation of clusters two (red) and cluster three (green).  In the K-Means Scatter Plot cluster three (green) is located far to the left of the main cluster while cluster one (red) was in the lower half of the main cluster.  In the PCA Scatter plot cluster one (red) has been relocated above and to the right of the main cluster while cluster three (green) has now been located far to the right of the main cluster.  One potential cause for these changes may be due to the 10.5% loss of variance that occurred during the PCA process.  It is also notable that the two relocated clusters are each comprised of only one node, representing a smaller cluster size.  This reduced cluster size could lead to wider fluctuations in data results when comparing across multiple models.   

<br>
<img src="Readme Pics/Compare Pic 2a.png" width="1163" height="247">

