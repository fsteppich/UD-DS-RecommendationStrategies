# Recommendations on the IBM Watson Studio Platform

This Project is intended to demonstrate different recommendation strategies.

Implemented are these strategies:
* Rank Based Recommendations
* User-User Based Collaborative Filtering
* Content-Based Recommendations (using Natural Language Processing (NLP) techniques)
* Matrix Factorization (Singular Value Decomposition (SVD))

These strategies get evaluated against a dataset contains technical articles from
the IBM Watson Studio Platform and a set of read-interactions between users and 
articles. 

Some ideas on how to take this project further are given in the section 
[Next Actions](#next_actions).


### Table of Contents

1. [Installation](#installation)
2. [File Descriptions](#files)
3. [Results](#results)
4. [Next Actions](#next_actions)
5. [Licensing, Authors, and Acknowledgements](#licensing)


## Installation and Dependencies<a name="installation"></a>
The project is running with Python 3. These libraries are required: 

* numpy
* pandas
* pickle
* matplotlib
* sklearn
* nltk
* re


## File Descriptions <a name="files"></a> 
`data/`

This folder containing the raw data (.csv-files) used in the Jupyter Notebook. 

`Recommendations.ipynb`

This is the primary file containing all the source code and information on each
part of the recommendation engine. 

`Recommendations.html`

An HTML-Export of the notebook for the purpose of review.

`project_tests.py`

Test code used in the Jupyter Notebook to evaluate the code performance 
(provided by [Udacity](https://www.udacity.com)).

`*.p`

Pickle files provided by [Udacity](https://www.udacity.com) to simplify the
code in the Juypter Notebook. 


## Results <a name="results">

**Rank-based Recommendations** are fairly simple as the only consider the number of 
interactions with each article.

**User-User Based Collaborative Recommendations** determine the similarity of users by 
comparing the reading profiles of the two users. If these users are sufficiently 
similar, it will recommend articles of the other user that this user did not read. 
Mitigation of the cold start problem is to fall back to the rank-based recommendation. 

**Content-Based Recommendations** analyze the text of an article and finds similar
articles by comparing the Term-Frequency-Inverse-Document-Frequency (TfIdf) 
representations.

**Matrix Factorization** computes the Singular-Value-Decomposition (SVD) of the 
user-item matrix. An issue arises from the fact, that the dataset is imbalanced.

## Next Actions <a name="next_actions">

This project only demonstrates the basic concept of a recommendation engine. To put all 
this into a useful product, one might take these actions: 

* Place the code in a python module (including unit tests) and make it accessible from 
	outside the notebook environment. 
* Evaluate ways to integrate the module with the IBM Watson Studio platform.
* If integration with the IBM Watson Studio platform is not possible it might still be
    possible to extract a current version of the dataset from the platform via API
    calls, perform and publish the recommendations on a web site, and/or a REST endpoint.
* Do better at splitting the dataset into a training and test dataset. Perform the split
	in a way that maximizes the number of users and articles intersecting in both sets.
* Implement an evaluation metric that is capable of measuring real-world user interactions.
* Improve the implementation of the Content-Based Recommendation to allow it to consider
	more articles and scale with increasing user requests and available articles. 

## Thanks, Authors, Acknowledgements<a name="licensing"></a> 
Any feedback that helps me to improve this project is welcome.  

You can find me on LinkedIn https://www.linkedin.com/in/fst/

This work is licensed under the GNU GPLv3 licence.

My thanks goes to [Udacity](https://www.udacity.com) for providing this insightful project
and to [IBM Watson Studio](https://cloud.ibm.com/) for providing the data.

