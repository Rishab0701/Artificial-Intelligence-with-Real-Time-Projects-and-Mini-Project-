This project is about creating a image recognition system to recognize currencies of different countries using Principle component analysis which is a unsupervised machine leaning algorithm that performs classification.
The dataset I am going to use in this project has around 60 images of currency of three countries which are China , Norway and Indonesia in separate folders where all these images are mosly in .jpg format and are rgb/color images only.
Here I mostly used scikit image library (skimage) to read the images from the directory , display the images , resize images , convert RGB images into grayscale images(so that the array size reduces from 3 to 2).

To make it easier and effective I am going to create class called as ImagepreProcessing which will have functions defined for executing process such as reading the images, converting all these images into gray scale images and finally resize all images into a single size for uniformity.
To extract more features from the image for more accurate image recognition I used histogram of oriented gradients algorithm imported as hog from scimage.feature
Hog is applied through iteration for each and every image in the directory so we can finally convert the all the images into histogram of oriented objects.
Now we have to flatten the obtained two dimensional into a single dimensional vector so using the flatten function from numpy module we are going to flatten and reshape the array.
Final step in image pre-processing is going to be converting array into a dateframe using panda module and create a new row with label as the name of the country whose currency we have processed.
Now Repeating all these steps for other two data sets (currency data) and  finally we get three data frame which are combined using concate function of panda module to create a final data frame.
Now the final dataframe is shuffled and dependent(country name) and independent variables are assigned ,then splitting the data in such a way that is going to be 25% of the total size for testing set and the training size will be remaining 75% by using train_test_splilt module of sklearn library ,
Then we are going to perfor PCA on the training dataset and then perform SVM finally we are going to give the test set of independent variable to the machine learning algorithm to predict the value here class/country.

We can infer that using Histogram of Oriented Gradients for processing the image and performing priciple component analysis are main reasons for the increased efficiency of the program and they can be infered based on the accuracy score which comes under performance metrics.

To verify how much the fitted data and the predicted data of the testing set we use performance metrics,in case of classification we use Confusion Matrix and Accuracy score they are functions of metrics module from sklearn library.
Both of them compare the predicted and test value to give accuracy score which in my project accuracy came out to be 75% from just svm and 82.5% from pca and confusion matrix which gives a matrix of 3 by 3 that give the number of correctly and incorrectly predicted values


