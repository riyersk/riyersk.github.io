---
layout: post
title: Project Luthor Reflection
---

This past Friday, we presented Project Luthor at Metis.  In brief, Project Luthor required us to scrape data from the internet and perform some sort of regression.
I chose to scrape data from boxofficemojo.com and to try and predict total domestic gross from a movie from various metrics pulled from the site.

On the whole, the project went decently, but there are two things I would have done differently were I to do it again.
First, I chose to eliminate all categorical variables (actor, director, rating, etc..).  Some were eliminated because there were too many categories and I didn't want to deal with a huge number of features.
Rating, the exception, was deleted because there was no statistically significant indicator that rating had an effect on total domestic gross.
What one of my cohort-mates did, however, was find the few actors who did appear to correlate with gross domestic total, and keep features corresponding to those actors.
I think this was a good idea, and I would choose to do something similar if I were to do this project again.

Second, what I was most proud of in this project was my idea for getting interaction terms without blowing up the features. Normally, if you use sklearn's PolynomialFeatures
with degree 2, for instance, the values of the features can get pretty large, so your coefficients have to be pretty extreme and can lead to overfitting easily. However,
if you take the square root of all your features before using polynomial features, you'll get your original terms back and interaction terms, and all of your features will keep a linear order of magnitude.
I extended this idea and explored third roots, sixth roots, ninth roots, and eighteenth roots, each with a range of model polynomial degrees. The best performing model with OLS was a degree 2 model with features taken to the 18th root.
However, I then committed to using 18th roots throughout the rest of the project.  This weekend, I went back and noticed that the performance varied between the different roots as I ran the code repeatedly.
If I were to do this again, I would test each root feature many times using each of the four models we learned about: OLS, Ridge, Lasso, and Elastic Net, in order to pick the best performing one.

As a final reflection, there are lots of functions data could potentially fit: the log function, polynomial functions of varying degrees, root functions, exponential functions, the gamma function, and the list goes on.
Sometimes, the number of potential features are many and it is not possible to examine each one and guess which kind of function should best represent that feature in the final model.
Moving forward, I'll be thinking of ways to try and automate the determination of feature functions to use, which interactions to keep, and what functions to use on those interactions.
As of right now, I'm thinking of training a neural network to recognize different functions amidst noise.
Whether this would do any better than simply training different models on different functions and picking the best performer, however, remains to be seen.
