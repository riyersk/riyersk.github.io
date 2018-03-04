---
layout: post
title: DBSCAN and cosine distance
---

For my latest project, I used scikit learn's DBSCAN clustering alrogithm with the cosine distance metric.  This metric can range from 0 to 2. 0 meaning that the two vectors in question are equal, and 2 meaning that they are opposite.  While I chose my epsilon (threshold for my DBSCAN algorithm. Basically, if the cosine distance between two vectors is greater than this epsilon, they are considered to not be in the neighborhood of one another.) by trial and error, I got to thinking if there was a more rigorous way to go about choosing it.  Using insights from [this derivation]("https://sites.math.washington.edu/~morrow/335_12/sphericalCoords.pdf") of spherical coordinates, I reasoned that the chance that two randomly chosen vectors in hyperspace would have a cosine distance less than k is just arccos(k)/pi, assuming k is from 0 to 1.

However, the epsilon I settled on after trial and error was .25.  Two randomly chosen vectors in hyperspace would have a cosine distance less than that about 23% of the time.  This seems really high, especially considering that I had about 20,000 vectors. (I actually had about 1.25 million vectors, but I couldn't use them all.  See previous blog post for explanation. However, even if I could have used them all, that would make a high epsilon even more concerning.) Well, the vectors generated from Doc2Vec are not randomly uniformly generated, but there probably is some sort of 'error' in their generation.

To do this properly, I'd have to go into the doc2vec implementation, figure out exactly how these vectors are generated, and see if I can model the 'error' so to speak, of these vectors.  That could lead to better insight into how to best choose epsilon.
