# Cluster Analysis with ALS Dataset

In this project I develop a K-Means clustering model with an ALS dataset. The data contains a plethora of different information on anonymized patients diagnosed with ALS.

I first remove features irrelevant to the patient's ALS condition (chiefly, the ID columns). Then I apply a standard scalar to the data. This helps make the features readily comparable as they are transformed to the same scale. Then, I create a plot of silhouette scores vs the number of clusters in a K-means cluster. I go from 2 clusters to 6 and looked at the silhouette score for each. The silhouette score gives us an idea of how good a given number of clusters fits the data. Across the board the silhouette scores were meager, all under .1 (of a maximum range of 1!). We chose 2 clusters as our optimal amount since it had the highest score.

I then create a K-Means model with 2 clusters and fit it to the scaled data.

Because of the large number of features in our data set, it is impossible to visualize the results of this clustering (that would be a graph in 40 dimensions). As such, I use Principal Component Analysis to reduce the number of features to better visualize the results of our cluster. I fit a PCA model to two features from our scaled data and then create a scatterplot of this data colored by which cluster it is in. 

What to take from this analysis? Firstly, the abysmal silhouette scores mean we should question the goodness of K-Means as an appropriate model for the data provided. In the visualization, the clusters partially overlap, there is little distinction between the two. This is not what we want from a clustering model; we want the clusters to be separate and well-defined. Further analysis should investigate other clustering model to see if there is a better approach. That said, we do still have 2 relatively well-identified clusters. The next step should be analyzing them further to investigate what those clusters may represent when it comes to ALS patients. We could do further visualization with selected features to see what it may mean for ALS patients to have these different clusters.
