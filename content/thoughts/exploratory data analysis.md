---
title: "Exploratory data analysis (EDA)"
date: 2022-09-09
tags:
  - seed
  - CPSC340
aliases:
  - EDA
---

How do we "look" at features and high-dimensional examples?

1. Summary statistics
   - Categorical Features
     - Frequencies
     - Mode
     - Quantiles
   - Numerical Features
     - Location
       - Mean
       - Median
       - Quantiles
     - Spread
       - Range
       - Variance
       - Interquartile ranges
   - [[thoughts/entropy|Entropy]]
   - [Not always representative](https://blog.revolutionanalytics.com/2017/05/the-datasaurus-dozen.html)! Don't mistake the map for the territory
2. Distance or similarities
   - Hamming distance: number of times elements aren't equal
   - Euclidian distance: how far apart are the vectors (square root of sum of squares)
   - Correlation
   - Jaccard coefficient: set distance, intersection over union
   - Edit distance: for strings, how many characters do I need to change to go from one to the other
   - [[thoughts/latent-factor model|Distance in latent space]]
3. Visualizations
   - Basic line plots
   - Matrix plot: visualize two features as an image
   - Correlation plot
     - Can add colour to show a third feature (usually categorical)
   - Scatterplot
