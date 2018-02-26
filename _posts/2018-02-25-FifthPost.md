---
layout: post
title: Project McNulty Reflection
---

On Wednesday, the 14th, we presented our second individual project, which was a classification project.  I chose to classify Lending Club loans, i.e., predict whether or not a given loan would charge off.

The details of how I went about the project can be found [in this repository]("https://github.com/riyersk/LCPredictionProject"), so I won't rehash it here.  What I want to do instead is speak to some thoughts that came to me while doing this project.

First, in an ideal world with infinite data, we could simply subset our data based on all categorical variables and then within each subset, build a separate model based on the remaining numeric variables. For example, if we had 3 categorical variables, A, B, and C, and A took on values 1 and 2, B took values 1, 2, and 3, and C took values 1 and 2, we'd split the data into 12 different groups, one for each combination of A,B, and C, and then build a separate model for each one.  For prediction, we would then simply pick the model that corresponded to the categorical values of the test data points and return the output of the corresponding model.

The problem is that we usually don't have nearly enough data to do this. Some of our subsets would have almost no training data, and some might even have none at all. So what do we do? The classic answer is random forest, where random subsets of features are chosen to build decision trees and the prediction is based on an ensemble vote.  My statistics is not at the point where I can confidently say that this is as good as the ideal system, or how close it gets, but we'll keep this in mind as the classic solution.

What I did for Project McNulty was to subset the data on one categorical variable that I thought would capture a lot of the variability, and then built models on each subset: a logistic regression and a random forest.  I thought this was a decent compromise, but what about a third way? What if we attempted to split the data up as we would in an ideal world, and then for the subsets that were sparsely populated, we did some sort of weighted ensemble vote between the closely related subsets?

I have to flush this idea out a bit more, answering questions on how you would pick the closely related subsets and how you'd choose the weights of the ensemble votes, but it's an interesting thought.

Second, once you've accounted for all categorical variables, the classification task is equivalent to drawing boundaries in n-dimensional hyperspace, where n is the number of numeric variables. I didn't do this for project McNulty, but one thing I'd make a point to try in the future is to gaussian boost the data based on the target class and then feed that feature into a logistic regression. We'd get the benefits of kernals in SVM along with LR's faster run time. Any sort of KNN would take a long time to train, but I'm wondering if there's a better way out there to draw these hyperspace boundaries.  More to think about!
