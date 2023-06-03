# Banknote-Authentication-ML
Implementing in Python the principle steps of the K-means algorithm. The project from course "Foundations of Data Science: K-Means Clustering in Python" by University of London &amp; Goldsmiths, University of London

## I. The purpose of the Data Science project
Nowadays, many banknotes may be faked. This project will use machine learning to automatically predict the detection of forged banknotes given the number of measures taken from photographs.

## II. Description of the data
>Data were extracted from images that were taken from genuine and forged banknote- like specimens. For digitization, an industrial camera usually used for print inspection was used. The final images have 400x 400 pixels. Due to the object lens and distance to the investigated object gray-scale pictures with a resolution of about 660 dpi were gained. Wavelet Transform tool were used to extract features from images.

The project dataset was simplified dataset of Bank Note Authentication UCI dataset. The dataset has 2 columns and 1372 rows (not null), in which contains 2 features
* V1. variance of Wavelet Transformed image
* V2. skewness of Wavelet Transformed image
<br>Data type: float64</br>
<br>Some mathematical distributions: mean, standard deviation, minimum, maximum, etc.</br>

## III. Methods: how the data were analyzed
<br>In the dataset there is only 2 features, and we don’t know the structure of the data yet. Furthermore, to find collections of observations that share similar characteristics, the K- means model is suitable to predict which banknote is genuine or forged.</br>

### Definition of K-means:
>“K-means clustering is a method for grouping n observations into K clusters. It uses vector quantization and aims to assign each observation to the cluster with the nearest mean or centroid, which serves as a prototype for the cluster. Originally developed for signal processing, K-means clustering is now widely used in machine learning to partition data points into K clusters based on their similarity. The goal is to minimize the sum of squared distances between the data points and their corresponding cluster centroids, resulting in clusters that are internally homogeneous and distinct from each other.”

<br> The project followed these steps to analyze the dataset:</br>
1. Data Exploration
2. Data Processing: *I removed duplicates and normalized the data for getting better prediction*
3. Modeling: training & predicting using K-means clustering 
4. Insights from Model


<br>The following libraries in the project:
* **Pandas** - used to read and write the csv file
* **Numpy** - used to perform mathematical operations
* **Matplotlib** - used to visualize the data in graphs
* **Scikit-learn** - used in k-means clustering
</br>

## IV. Summary of the results
<br>I run the K-Means clustering model 5 times, the centroids of the clusters varied slightly, which shows that the model is stable.</br>
<br>The dataset divided into 2 clusters for forged and authentic. As from the scatter plot, the results of model predicted blue area for genuine banknotes, the green area for forged banknotes.</br>
<br>Then I compared the result with the original dataset [OpenML](https://www.openml.org/d/1462), which contains actual classes to see how much percentage the model is correct. After normalization, I got 1197/1372 matched rows, means 87,2% correctness of prediction using K-means clustering.</br>

## V. Recommendations
<br>From the prediction, client can be able to identify which banknote is authentic. The dataset prediction will be better with more features. Client should do more tests on banknotes which are classified as forged banknote and real ones.</br>
<br>The higher the skewness and variance of Wavelet Transformed image is, the higher chance the banknote is authentic.</br>
