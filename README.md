# Support_vector_machines

A support vector machine is a very powerful and versatile Machine learning model, capable of performing linear or nolinear classification, regression and even outlier detection.


SVMs are particularly well suited for classification of complex but small- or medium sized datasets.


## Linear SVM Classification

You can think of an SVM classifier as fitting the widest street (represented by the parallel dashed lines) between the classes.
This is called large margin classification.

SVMs are sensitive to the feature scales.


## Soft Margin Classification
If we strictly impose that all instances be off the street and on the right side, this is called hard margin classification.

The objective of SMC is to find a good balance between keeping the street as large as possible and limiting the margin violations.

In scikit learn you can control this balance using the C hyperparameter: a smaller C value leads to a wider street but more margin violations.


## NonLinear SVM Classification

An approcah to handle nonlinear datasets is to add more features, such as polynomial features.
To implement the idea in scikit learn, you can create a Pipeline containing a PolynomialFeatures transformer.


## Polynomial Kernel

Adding polynomial features is simple to implement and can work great with all sorts of ML algorithms, but at a low polynomial degree it cannot deal with very complex datasets, and at high polynomial degree it creates a huge number of features, making the model slow.

Fortunately, when using SVMs you can apply an almost miraculous mathematical technique called the kernel trick


## Adding Similarity Features

Another technique to tackle nonlinear problems is to add features computed using a similarity function that measures how much each instance resembles a particular landmark.

To select a landmark, simply create a landmark at the location of each and every instance in the dataset. This create many dimensions and thus increases the chances that the transformed training set will be linearly separable.



## Gaussian RBF Kernel

As a rule of thumb, you should always try the linear kernel first ( remember that LinearSVC is much faster than SVC(kernel = "linear")), especially if the training set is very large or if it has plenty of features.

If the training set is not too large, you should try the Gaussian RBF kernel as well; it works well in most cases.


## Computation Complexity

## SVM Regression

The trick here is to reverse the objective: Instead of trying to fit the alrgest possible street between two classes while limiting margin violations, SVM Regression tries to fit as many instances as possible on the street while limiting margin violations.

