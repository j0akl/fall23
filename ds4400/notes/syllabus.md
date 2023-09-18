# Syllabus

Refer to online doc

When emailing, title the email DS4400 JAKE LYNN or something like that

HW regrades need to be submitted within one week of the grading

ChatGPT allowed, but not really for full assignments. Use wisely

Slides and notes posted online

## Supervised Learning

Learning where the data is labelled.

Classification:
- Predict descrete classes
Regression: 
- predict a response variable (numerical)
- minimize error between prediction and actual values (MSE)

## Unsupervised Learning

Learning where the data is not labelled.

- Relating variables to one another
- shrinking dimensionality

- Clustering:
  - clustering data points, _k_-means, 
- Dimensionality Reduction:
  - projecting data to a lower dimensional space
  - PCA (Principal Component Analysis)
- Feature Learning:
  - Find feature representation
  - Autoencoders

## Examples (Identify Guess/Actual)
- Predict Tomorrows Temp: Supervised/Supervised
- Predict whether tomorrows temp is over 75: Supervised/Supervised
- Sudents like to be friends with similar people: Unsupervised (? oddly formed question)/Unsupervised(clustering)
- Distinguish freshman: Supervised/Supervised(classification)
- Put students in groups by major: Supervised/Unclear, target value but also a clustering problem. More supervised than unsupervised(classification)
- Look for genes that are similar to each other: Unsupervised/

Generally easier to convert regression to classification

## Dataframes

Usually, we will clean data and put in in a DF

Variables in Cs are called "Features" (Columns)
- there are target (response) variables and explanatory (input) variables

Samples are rows

Observations are generally assumed to be independent, but in real life data this is not always true

Types of variables:
- numerical
- categorical (enums)
- others (string)

We won't do much data cleaning in this class, but be given clean data

## Matricies

In order to run our data through a model, we will need to convert out DF entries to matricies

## Linalg review

+/-, elementwise, must have same dimension

Multiplication: A in R^(m\*x) B in R^(n\*p) rows times columns *Review this*

Transpose: Flip dimensions

Inverse: A \* A^-1 = *I*

Often, we wont care about individual data points. We may only care about something like the max
value of a column, or the average





