**CS5785Homework1![](CS5785\_Homeworks\_2020Fall\_\_1\_.001.png)![](CS5785\_Homeworks\_2020Fall\_\_1\_.002.png)**

The homework is generally split into programming exercises and written exercises.![](CS5785\_Homeworks\_2020Fall\_\_1\_.003.png)

This homework is due on **October 1, 2020 at 11:59 PM ET**. Upload your homework to Gradescope (Canvas->Gradescope). There are two assignments for this homework in Gradescope. Please note a complete submission should include:

1. A write-up as a single .pdf file. ¡! Submit to “Homework 1- Write Up”.
1. Source code for all of your experiments (AND figures) zipped into a single .zip file, in .py files if you use Python or .ipynb filesif you use the IPython Notebook. If you use some other lan- guage, include all build scripts necessary to build and run your projectalong with instructions on how to compile and run your code. **IfyouusetheIPythonNotebooktocreateanygraphs, please makesureyou alsoincludethem.** ¡! Submit to “Homework 1- Code”.

The write-up should contain a general summary of what you did, how well your solution works, any insights you found, etc. On the cover page, include the class name, homework number, and team member names. You are responsible for submitting clear, organized answers to the questions. You could use online LATEX templates from Ove[rleaf, und](https://www.overleaf.com/latex/templates/)er “Homework Assignment” or “Project / Lab Report”.

Please include all relevant information for a question, including text response, equations, figures, graphs, output, etc. If you include graphs, be sure to include the source code that generated them. Please pay attention to Canvas for relevant information regarding updates, tips, and policy changes. You are encouraged (but not required) to work in groups of 2.

IF YOU NEED HELP

There are several strategies available to you.

- If you get stuck, we encourage you to post a question on the Discussions section of Canvas. That way, your solutions will be available to other students in the class.
- The professor and TAs offer office hours, which are a great way to get some one-on-one help.
- You are allowed to use well known libraries such as scikit-learn, scikit-image, numpy, scipy, etc. forthisassignment. Anyreferenceorcopyofpubliccoderepositoriesshouldbeproperlycited in your submission (examples include Github, Wikipedia, Blogs).
CS5785 Fall 2020: Homework 1 Page PAGE4

PROGRAMMING EXERCISES

1. Digit Recognizer
1) Join the [Digit Recognizer compet](http://www.kaggle.com/c/digit-recognizer)ition on Kaggle. Download the training and test data. The competition page describes how these filesare formatted.
1) Write a function to display an MNIST digit. Display one of each digit.
1) Examine the prior probability of the classes in the training data. Is it uniform across the digits? Display a normalized histogram of digit counts. Is it even?
1) Pickoneexampleofeachdigitfromyourtrainingdata. Then,foreachsampledigit,compute and show the best match (nearest neighbor) between your chosen sample and the rest of the training data. Use *L*2 distance between the two images’ pixel values as the metric. This probably won’t be perfect, so add an asterisk next to the erroneous examples (if any).
1) Consider the case of binary comparison between the digits 0 and 1. Ignoring all the other digits, compute the pairwise distances for all genuine matches and all impostor matches, againusingthe *L*2 norm. Plothistogramsofthegenuineandimpostordistancesonthesame set of axes.
1) Generate an R[OC curve fr](https://scikit-learn.org/stable/modules/model_evaluation.html#receiver-operating-characteristic-roc)om the above sets of distances. What is the equal error rate? What is the error rate of a classifier that simply guesses randomly?
1) Implement a K-NN classifier. (You cannot use external libraries for this question; it should be your own implementation.)
1) Take 15% of your dataset and make it your holdout set. Train the classifieron the remaining data, using different values of *K* and use the holdout set to determine the best value of *K*. Print a table showing the values of *K* you tried as well as their training and holdout accuracy. Report the best value of *K* that you found.
1) Generate a c[onfusion matrix (of ](https://scikit-learn.org/stable/modules/model_evaluation.html#confusion-matrix)size 10 £ 10) from your results. Which digits are particularly tricky to classify?
1) Train your classifier with all of the training data, and test your classifier with the test data. Submit your results to Kaggle.
2. Predicting House Prices
1) Join the [House Prices compet](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)ition on Kaggle. Download the training and test data.
1) Using least squares, try to predict house prices on this dataset. You can choose the features (or combinations of features) you would like to use or ignore, provided you justify your rea- soning.
1) Now try predicting house prices using regularized least squares. Try both L1 and L2 regu- larization and compare them. Briefly describe your findings from training regularized and unregularized models.
1) Train your model using all of the training data, and test it using the testing data. Submit your results to Kaggle.
PAGE4
CS5785 Fall 2020: Homework 1 Page NUMPAGES6![](CS5785\_Homeworks\_2020Fall\_\_1\_.004.png)

WRITTEN EXERCISES

1. Maximum Likelihood and KL Divergence. Let *p*ˆ(*x*,*y*) denote the empirical data distribution over

a space of inputs *x* 2 X and outputs *y* 2 Y . For example, in an image recognition task, *x* can be an image and *y* can be whether the image contains a cat or not. Let *pµ*(*y*j*x*) be a probabilistic classifierparameterized by *µ*, e.g., a logistic regression classifierwith coefficients *µ*. Show that the following equivalence holds:

£ ¤ £ ¤

argmax E*p*ˆ(*x*,*y*) log *pµ*(*y*j*x*) Æargmin E*p*ˆ(*x*) KL(*p*ˆ(*y*j*x*)k*pµ*(*y*j*x*)) .

*µ*2£ *µ*2£

where KL denotes the KL-divergence:

KL(*p*(*x*)k*q*(*x*)) ÆE*x*» *p*(*x*)[log *p*(*x*) ¡ log *q*(*x*)].

2. Bayes rule for quality control. You’re the foreman at a factory making ten million widgets per year. As a quality control step before shipment, you create a detector that tests for defective widgets be- fore sending them to customers. The test is uniformly 95% accurate, meaning that the probability of testing positive given that the widget is defective is 0.95, as is the probability of testing negative given that the widget is not defective. Further, only one in 100,000 widgets is actually defective.
1) Suppose the test shows that a widget is defective. What are the chances that it’s actually defective given the test result?
1) If we throw out all widgets that are test defective, how many good widgets are thrown away per year? How many bad widgets are still shipped to customers each year?
3. In *k*-nearest neighbors, the classification is achieved by majority vote in the vicinity of data. Sup- pose our training data comprises *n* data points with two classes, each comprising exactly half of the training data, with some overlap between the two classes.
1) Describe what happens to the average 0-1 prediction error on the training data when the neighbor count *k* varies from *n* to 1. (In this case, the prediction for training data point *xi* includes (*xi*,*yi*) as part of the example training data used by *k*NN.)
1) We randomly choose half of the data to be removed from the training data, train on the re- maininghalf,andtestontheheld-outhalf. Predictandexplainwithasketchhowtheaverage 0-1 prediction error on the held-out validation set might change when *k* varies? Explain your reasoning.
1) In *k*NN,once *k* isdetermined,allofthe *k*-nearestneighborsareweightedequallyindeciding the class label. This may be inappropriate when *k* is large. Suggest a modification to the algorithm that avoids this caveat.
PAGE6
