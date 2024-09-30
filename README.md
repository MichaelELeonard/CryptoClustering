<img src="Readme Pics/Opening Pic.png" width="1000" height="300">

# Unsupervised Machine Learning - Crypto Clustering

[Unsupervised Learning Modeling Code Link]( https://github.com/MichaelELeonard/CryptoClustering/blob/main/Crypto_Clustering_working.ipynb)

## Original Data

In the Unsupervised Machine Learning Challenge, we were tasked to predict how cryptocurrencies will be affected by 24-hour or 7-day price changes.  This was accomplished by completing a K-Means and PCA analysis and comparing the results.  The original data was provided in a .csv file and was imported to a DataFrame for analysis.  The initial DataFrame output and line graph representing the data can be seen below.     

<br>
<img src="Readme Pics/Original Data.png" width="1201" height="259">
<img src="Readme Pics/Original Data Graph.png" width="671" height="336">


## Crypto Clustering with K-MEANS

To start the analysis, the data needed to be scaled to ensure consistency throughout the dataset.  This was accomplished by using StandardScaler which is available in the scikit-learn library.  An example of the scaled data can be seen below.   

<img src="Readme Pics/Scaled data.png" width="1184" height="148">

Next, the best value for K needed to be calculated.  The data was plotted to an elbow curve to identify the best value for K.  The results identified the optimal value to K to be four.    
<br>
<img src="Readme Pics/K-Means Elbow.png" width="585" height="252">

A model instance was initiated using the optimal four clusters, fit to the original scaled data, and run to predict the crypto clusters.  Finally, the predicted clusters were added to the DataFrame and a scatterplot was used to view the results.  The results showed a reasonable correlation between the blue, red and gold clusters, with the green cluster located to the left of the main cluster.        
<br>
<img src="Readme Pics/Scaled data with Predicted Clusters.png" width="1275" height="164">
<img src="Readme Pics/K-Means Scatter.png" width="579" height="245">
<br>

## Crypto Clustering with PCA 
For the PCA analysis, pca.fit _transform was used on the original scaled data to manipulate it into three principal components.  After checking the variance ratio for the newly aligned data, the three groups were shown to represent 89.49% of the variance of the dataset with a 10.51% variance loss.

<img src="Readme Pics/PCA Three Components.png" width="385" height="114">
<img src="Readme Pics/PCA Three Component Variance.png" width="327" height="40">


The data was plotted to an elbow curve to identify the best value for K.  The ideal value for K was identified as four.

<img src="Readme Pics/PCA Elbow.png" width="587" height="252">


The cluster results were added to the PCA DataFrame and it was used to produce a scatterplot below.  In the PCA scatterplot, the gold and blue clusters are produced similar results while the red and green clusters are to the right of the main cluster. 

<br>
<img src="Readme Pics/PCA Three Components with Clusters.png" width="436" height="186">
<img src="Readme Pics/PCA Scatter.png" width="581" height="248">


## Results/Comparison

When examining the two elbow curves, the results share similar characteristics with both graphs identifying the optimal number for K as four.    

<br>

<img src="Readme Pics/Compare Elbow.png" width="1166" height="249">


The two scatterplots produced mixed results showing commonalities and exposing some differences.  In both scatterplot images, the gold and blue clusters comprise the main cluster and show similar results between the two plots.  Both main clusters maintained a consistent range on the X and Y axis, and both produced a small amount of overlap between the two clusters.  The main difference between the two scatterplots can be seen with the location of red and green clusters.  In the K-Means plot the green cluster is located far to the left of the main cluster while the red cluster was in the lower half of the main cluster.  In the PCA scatterplot, the red cluster has been located above and to the right of the main cluster while the green cluster is located to the right of the main cluster.  One potential cause for this result may be due to the 10.5% loss of variance that occurred during the PCA process.  It is also notable that the red and green clusters are each comprised of only one node, representing a small cluster size.  This reduced cluster size could lead to wider fluctuations in data results when comparing across multiple models.   

<br>
<img src="Readme Pics/Compare Scatter.png" width="1163" height="247">

