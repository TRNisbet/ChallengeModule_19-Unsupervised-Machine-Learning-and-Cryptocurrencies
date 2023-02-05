# ChallengeModule_19-Unsupervised-Machine-Learning-and-Cryptocurrencies
ChallengeModule_19-Unsupervised-Machine-Learning-and-Cryptocurrencies

Module 19 Challenge

Background
You and Martha have done your research. You understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. It’s time to put all these skills to use by creating an analysis for your clients who are preparing to get into the cryptocurrency market.

Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

What You're Creating
This new assignment consists of four technical analysis parts. You will submit the following:

Part 1: Preprocessing the Data for PCA
Part 2: Reducing Data Dimensions Using PCA
Part 3: Clustering Cryptocurrencies Using K-means
Part 4: Visualizing Cryptocurrencies Results
Files
Use the following links to download the dataset and Challenge starter code.

Download Challenge starter filesLinks to an external site.

Instructions
Part 1: Preprocessing the Data for PCA (30 points)
Using your knowledge of Pandas, you’ll preprocess the dataset in order to perform PCA in Part 2.

Follow the instructions below and use the crypto_clustering_starter_code.ipynb file to complete Part 1.

Open the crypto_clustering_starter_code.ipynb file, rename it crypto_clustering.ipynb, and save it to your Cryptocurrencies GitHub folder.

Read in the crypto_data.csv to the Pandas DataFrame named crypto_df.

NOTE
The crypto_data.csv was retrieved from CryptoCompare Links to an external site..

Keep all the cryptocurrencies that are being traded.

Drop the IsTrading column.

Remove rows that have at least one null value.

Filter the crypto_df DataFrame so it only has rows where coins have been mined.

Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.

Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.

Take a moment to check that your crypto_df DataFrame looks like the image below:

The crypto_df DataFrame shows four  columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply. It contains ten rows with the following headings: 42, 404, 1337, BTC, ETH, LTC, DASH, XMR, ETC, and ZEC
Use the get_dummies() method to create variables for the two text features, Algorithm and ProofType, and store the resulting data in a new DataFrame named X.

Use the StandardScaler fit_transform() function to standardize the features from the X DataFrame.

IMPORTANT
Using the StandardScaler() sklearn library to standardize the features is required before attempting Parts 2 and 3.

Save your crypto_clustering.ipynb file to your Cryptocurrencies folder.

Part 2: Reducing Data Dimensions Using PCA (20 points)
Using your knowledge of how to apply the Principal Component Analysis (PCA) algorithm, you’ll reduce the dimensions of the X DataFrame to three principal components and place these dimensions in a new DataFrame.

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Part 2.

Continue using the crypto_clustering.ipynb file from Part 1 where you’ve already performed the preprocessing steps.

Using the information we’ve provided, apply PCA to reduce the dimensions to three principal components.

If you’d like a hint on how to use the PCA algorithm, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

HINT
Refer to the PCA algorithm from sklearn documentation Links to an external site.to reduce the dimensions of the X DataFrame down to three principal components.

Create a new DataFrame named pcs_df that includes the following columns, PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.

Your DataFrame should look like the image below:

data-Module-18-Challenge-1-clustering-cryptocurrencies-using-k-means.png
Save your crypto_clustering.ipynb file to your Cryptocurrencies folder.

Part 3: Clustering Cryptocurrencies Using K-means (20 points)
Using your knowledge of the K-means algorithm, you’ll create an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame created in Part 2. Then, you’ll run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Part 3.

Continue using the crypto_clustering.ipynb file that you used in Part 2 to reduce the dataset to three dimensions.

Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K.

Next, use the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.

If you’d like a hint on how to use the K-means algorithm, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

HINT
Refer to the KMeans algorithm from sklearn documentation Links to an external site.to help you cluster the cryptocurrencies using the PCA data.

Create a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns. The index should be the same as the crypto_df DataFrame.

Add the CoinName column that holds the names of the cryptocurrencies, which you created in Step 7 of Part 1, to the clustered_df.

Add another new column to the clustered_df named Class that holds the predictions, i.e., model.labels_, from Step 3.

Your clustered_df DataFrame should look like the image below:

The DataFrame shows nine columns: Algorithm, ProofType,TotalCoinsMined, TotalCoinSupply, PC1, PC 2, PC 3, CoinName, and Class.It contains ten rows with the following headings: 42, 404, 1337, BTC, ETH, LTC, DASH, XMR, ETC, and ZEC.
Save your crypto_clustering.ipynb file to your Cryptocurrencies folder.

Part 4: Visualizing Cryptocurrencies Results (30 points)
Using your knowledge of creating scatter plots with Plotly Express and hvplot, you’ll visualize the distinct groups that correspond to the three principal components you created in Part 2, then you’ll create a table with all the currently tradable cryptocurrencies using the hvplot.table() function.

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Part 4.

Continue using the crypto_clustering.ipynb file from Part 3 where you have predicted the K clusters for the cryptocurrencies’ data.

Create a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.

Add the CoinName and Algorithm columns to the hover_name and hover_data parameters, respectively, so each data point shows the CoinName and Algorithm on hover.

If you’d like a hint on how to add additional parameters to a Plotly Express 3D scatter plot, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

HINT
Refer to the scatter_3d() documentation Links to an external site.to add additional parameters to a Plotly Express 3D scatter plot.

Create a table with tradable cryptocurrencies using the hvplot.table() function.

If you’d like a hint on how to use the hvplot.table() function, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

HINT
Refer to the hvplot.table() documentation Links to an external site.to create a table with tradable cryptocurrencies.

Your table should look like the table in the image below:

An hvplot.table() showing all the tradable cryptocurrencies with six  columns: CoinName, Algorithm, ProofType, TotalCoinSupply, TotalCoinsMined, and Class
Print the total number of tradable cryptocurrencies in the clustered_df DataFrame.

Use the MinMaxScaler().fit_transform method to scale the TotalCoinSupply and TotalCoinsMined columns between the given range of zero and one.

If you’d like a hint on how to use the MinMaxScaler().fit_transform method to scale the "TotalCoinSupply" and "TotalCoinsMined" columns, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

HINT
Refer to the MinMaxScaler().fit_transform documentation Links to an external site.to scale the features.

Create a new DataFrame using the clustered_df DataFrame index that contains the scaled data you created in Step 5.

Add the CoinName column from the clustered_df DataFrame to the new DataFrame.

Add the Class column from the clustered_df DataFrame to the new DataFrame.

Your new DataFrame should look similar to the image below:

A tradable cryptocurrencies DataFrame showing four columns: , TotalCoinSupply, TotalCoinsMined, CoinName, and Class. It contains ten rows with the following headings: 42, 404, 1337, BTC, ETH, LTC, DASH, XMR, ETC, and ZEC.
Create an hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class", and have it show the CoinName when you hover over the the data point.

If you’d like a hint on how to add the CoinName column data when you hover over a data point, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

HINT
Refer to the hvplot Customization documentation Links to an external site.to apply additional options to Holoviz plots.

Your scatter plot should look similar to the image below:

A hvplot scatter plot with X-axis as the "TotalCoinsMined", Y-axis as the "TotalCoinSupply", ordered by "Class", and when you hover over each data point it shows the "CoinName". 
Save your crypto_clustering.ipynb file to your Cryptocurrencies folder.

Requirements
Part 1: Preprocessing the Data for PCA (30 points)
You will earn a perfect score for Part 1 by completing all requirements below:

The following five preprocessing steps have been performed on the crypto_df DataFrame:
All cryptocurrencies that are not being traded are removed (3 points)
The IsTrading column is dropped (3 points)
All the rows that have at least one null value are removed (3 points)
All the rows that do not have coins being mined are removed (3 points)
The CoinName column is dropped (3 points)
A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame (5 points)
The get_dummies() method is used to create variables for the text features, which are then stored in a new DataFrame, X (5 points)
The features from the X DataFrame have been standardized using the StandardScaler fit_transform() function (5 points)
Part 2: Reducing Data Dimensions Using PCA (20 points)
You will earn a perfect score for Part 2 by completing all requirements below:

The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components (10 points)
The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame (10 points)
Part 3: Clustering Cryptocurrencies Using K-means (20 points)
You will earn a perfect score for Part 3 by completing all requirements below:

The K-means algorithm is used to cluster the cryptocurrencies using the PCA data, where the following steps have been completed:
An elbow curve is created using hvPlot to find the best value for K (10 points)
Predictions are made on the K clusters of the cryptocurrencies’ data (5 points)
A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class (5 points)
Part 4: Visualizing Cryptocurrencies Results (30 points)
You will earn a perfect score for Part 4 by completing all requirements below:

The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover (10 points)
A table with tradable cryptocurrencies is created using the hvplot.table() function (3 points)
The total number of tradable cryptocurrencies is printed (2 pt)
A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns (5 points)
A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point (10 points)
Grading
This assignment will be evaluated against the requirements and assigned a grade according to the following table:

Grade	Points
A (+/-)	90+
B (+/-)	80–89
C (+/-)	70–79
D (+/-)	60–69
F (+/-)	< 60
Submission
Once you’re ready to submit, make sure to check your work against the requirements for this Challenge one final time. It’s easy to overlook items when you’re in the zone!

As a reminder, the parts for this Challenge are as follows:

Part 1: Preprocessing the Data for PCA
Part 2: Reducing Data Dimensions Using PCA
Part 3: Clustering Cryptocurrencies Using K-means
Part 4: Visualizing Cryptocurrencies Results
Upload the following to your Cryptocurrencies GitHub repository:

Your crypto_clustering.ipynb file.
A README.md that includes the purpose of the repository and short description of what was accomplished. Although there is no graded written analysis for this challenge, it is encouraged and good practice to add a brief description of your project.
To submit your challenge assignment for grading in Bootcamp Spot, click Start Assignment, click the Website URL tab, then provide the URL of your Cryptocurrencies GitHub repository, and then click Submit. Comments are disabled for graded submissions in BootCampSpot. If you have questions about your feedback, please notify your instructional staff or the Student Success Manager. If you would like to resubmit your work for an improved grade, you can use the Re-Submit Assignment button to upload new links. You may resubmit up to 3 times for a total of 4 submissions.

IMPORTANT
Once you receive feedback on your Challenge, make any suggested updates or adjustments to your work. Then, add this week’s Challenge to your professional portfolio.

NOTE
You are allowed to miss up to two Challenge assignments and still earn your certificate. If you complete all Challenge assignments, your lowest two grades will be dropped. If you wish to skip this assignment, click Next, and move on to the next Module.

