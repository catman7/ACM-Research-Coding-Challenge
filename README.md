# ACM Research Coding Challenge (Fall 2020)

## No Collaboration Policy

**You may not collaborate with anyone on this challenge.** You _are_ allowed to use Internet documentation. If you _do_ use existing code (either from Github, Stack Overflow, or other sources), **please cite your sources in the README**.

## Submission Procedure

Please follow the below instructions on how to submit your answers.

1. Create a **public** fork of this repo and name it `ACM-Research-Coding-Challenge`. To fork this repo, click the button on the top right and click the "Fork" button.
2. Clone the fork of the repo to your computer using . `git clone [the URL of your clone]`. You may need to install Git for this (Google it).
3. Complete the Challenge based on the instructions below.
4. Email the link of your repo to research@acmutd.co with the same email you used to submit your application. Be sure to include your name in the email.

## Question One

![Image of Cluster Plot](ClusterPlot.png)
<br/>
Given the following dataset in `ClusterPlot.csv`, determine the number of clusters by using any clustering algorithm. **You're allowed to use any Python library you want to implement this**, just document which ones you used in this README file. Try to complete this as soon as possible.

Regardless if you can or cannot answer the question, provide a short explanation of how you got your solution or how you think it can be solved in your README.md file.



## ANSWER: 
Libraries: sci-kit learn, numpy, matplotlib, & kneed.

To determine the number of clusters in this dataset I would implement a DBSCAN clustering algorithm. I got to this solution by researching about different clustering algorithms, watching youtube videos, and saw how this one automatically determines the amount of clusters rather than K Means, in which you have to guess and go through trial and error without choice. DBSCAN allows us to find any cluster regardless of shape. 

First, I notice how there are 2 "spots" or groupings on the graph which indicate atleast 2 clusters and they have a couple of points that seem like outliers. Using DBSCAN we can identify outliers without any skewing. I would set my eps (epsilon: the maximum distance that helps determine if 2 points are neighbors) to be 1.5 and my minpts/min_samples to be 15. From here on out, I would approach with more trial and error with the eps & minpts values to see what provides us with the most satisfactory result in clustering the points. One of the ways we can find a good EPS range is by using the "kneed" library which allows us to find a "knee" point which would be the most optimal eps value. DBSCAN allows us to have 3 kinds of points: Core points, border points, and noise points. Core points are points in which a point has atleast the minpts amount of points within its eps range. Border points are those in which a point, within its eps range, has less than the initialized amount of minpts from the beginning. Noise points are basically outliers where there are no other points within its range. After implementing these processes, the DBSCAN algorithm should detect the appropriate amount of clusters in the plot. 

Citations:
Mallawaarachchi, V. (2020, June 21). How to Use DBSCAN Effectively. Retrieved September 07, 2020, from https://towardsdatascience.com/how-to-use-dbscan-effectively-ed212c02e62


Yıldırım, S. (2020, April 22). DBSCAN Clustering - Explained. Retrieved September 07, 2020, from https://towardsdatascience.com/dbscan-clustering-explained-97556a2ad556


Chauhan, N. (2020). DBSCAN Clustering Algorithm in Machine Learning. Retrieved September 07, 2020, from https://www.kdnuggets.com/2020/04/dbscan-clustering-algorithm-machine-learning.html

