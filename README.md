# Understanding the Genetic Code — Data Analysis with K-means and PCA

This project explores how unsupervised learning techniques—specifically K-means clustering and Principal Component Analysis (PCA)—can help us uncover patterns in DNA sequences to better understand the genetic code.

## Overview

DNA is essentially a sequence of four letters: A, C, G, and T. These letters form a kind of code that provides instructions for the development and functioning of living organisms.

In this analysis, we examine whether DNA can be thought of as being composed of "words" of equal length, and if so, how long those words might be.

## Data Preparation

We use a real DNA fragment from Caulobacter Crescentus, a bacterium.

The dataset contains about 305,100 letters, split into 1,017 non-overlapping sequences of 300 letters each.

For each proposed word length M (1, 2, 3, or 4), we count the frequency of every possible word (e.g., for M=2, there are 16 possible two-letter combinations).

These counts form the features of our dataset, which can have up to 256 dimensions when M=4.

## Dimensionality Reduction with PCA

Since it’s difficult to visualize high-dimensional data, we use PCA to reduce the dataset to two principal components.
This allows us to explore structure and symmetry in the data visually.

<p align="center">
  <img src="[PIC_1](https://github.com/Mitzay/Genomic-Data-Clustering/blob/main/PIC_1.png?raw=true)" alt="Alt text" width="400">
</p>

Interestingly, clear structure appears only when M = 3, suggesting that DNA may naturally encode information in three-letter “words.”

## Clustering with K-means

We standardize the data and run K-means clustering for different numbers of clusters (K = 6 and K = 7).
The results align closely with the PCA visualization, revealing distinct clusters even in the high-dimensional space.

👉 [Insert K-means clustering result plot here — showing 7 clusters (6 outer lobes + 1 central cluster)]

When K = 7, the visualization separates the central blob from six symmetrical lobes:

The six lobes correspond to the six possible reading directions of DNA (three forward, three backward).

The central cluster represents non-coding DNA, regions that don’t encode proteins.

## Insights

From this analysis, we find:

DNA sequences naturally organize into three-letter words, known as codons.

Each codon encodes an amino acid, the building blocks of proteins.

K-means and PCA effectively reveal biological structure from raw sequence data.

## Conclusion

Using simple unsupervised learning methods, we can extract meaningful biological insights from raw genetic data. This approach demonstrates the power of machine learning to uncover patterns hidden within complex natural systems.
