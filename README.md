# FYS-2021-Machine-Learning
Assignments for Machine Learning

# FYS-2021 Assignment 1

## Problem 1 – Introduction 

#### (1a)
First, we load the SpotifyFeatures CSV file with the Pandas module, then we retrieve the features and the associated data (feature_data). The length of the arrays are the number of samples and number of features of the dataset, respectively.
 
#### (1b)
Now we take out the songs that are classified as pop or classical, and put it in filtered_data. Then we change the labels to be 1 if it is a pop song, and 0 if it is not (a classical song). To know the amount of pop and classical songs, we take the length of the filtered_data when the label is 1 and when the label is 0. 
 
#### (1c)
For the rest of the assignment, we are only interested in the liveness and loudness features. We extract them and put them in a X matrix, with liveness as the first column and loudness as the second column. Our y will be the classification, 1 or 0. 
To split the dataset, we use the sklearn module. We use an 80/20 % split, meaning that 80% of the dataset is used to train our model. From this we get a model that can predict new y-values (1 or 0). To test our model, we use the remaining 20% to test our model and check the accuracy. In addition, we split the data per class to keep the same class distribution. Also, we shuffle the data (songs are fed to the classifier in random order). 
 
#### (1d) [Bonus]
Plotting the pop and classical songs with loudness on the y-axis and liveness on the x-axis. We can see that the classification can be somewhat difficult since there are pop and classical songs that overlaps, especially when it is high loudness and low liveness (upper left corner in plot).

 
## Problem 2 - Machine learning with Logistic Regression 
#### (2a)
Logistic Regression is based on the Sigmoid function. This function will give a y-value between 0 and 1, where 0.5 is the boundary between the two classes.
To do Logistic Regression we start with some weights w and bias b, and then use Gradient descent to find the most optimal weights and bias. In gradient descent, you use the following equations to find the minimum: w\ =\ w\ -\ \alpha\ \ast\ dw , and b\ =\ b\ -\ \alpha\ \ast\ db
where \alpha is the learning rate and the gradients, dw and db, is defined as: dw\ =\ X\ \ast\ (\hat{y}\ -\ y) , and db\ =\sum{\hat{y}\ -\ y}
(In this assignment I have used w and b separately, but you could put them together in a common matrix)
 
To train the set, we use 80% of the dataset. We make the logistic regression to a function and iterate it multiple times (epochs). In the first iteration, we start with weight and bias equal to zero, and then for the next iteration we take the last epochs weights and bias to optimize it more. 
We also calculate the cross-entropy loss to check the error.
 
To see what the best learning rate is, we can look at the accuracy for the different learning rates. We do that by comparing the predicted y-values with the actual values in the y train set. From this comparison, we can calculate the accuracy (how often our model is correct in the prediction).
 
We see that the lowest learning rate, 0.001, gives the best accuracy with 92.57%. So, with this learning rate, we get the most optimal weights and bias that we can use in the sigmoid function to predict new values.

#### (2b)
Now we have learned our model, we can test it on the test set and look at the accuracy.

#### (2c) [Bonus]
From the plot we can see the classification between the genres in the liveness and loudness plane. 
 
## Problem 3 – Results 
#### (3a)
Using the classification results from the test set in problem 2b, we can create a confusion matrix for the classification from the sklearn module.

#### (3c) [Bonus]
A Classical song that a Pop fan would like, is a song that is classical but got predicted wrong as pop by the model.  
