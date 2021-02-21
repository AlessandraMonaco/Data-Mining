# AN IMPLEMENTATION OF LOCALITY SENSITIVE HASHING FOR DUPLICATES DETECTION IN AMAZON PRODUCT DESCRIPTIONS

## Introduction
Nearest duplicate search is a very used task in text mining. Anyway, the Naive Approach of comparing every possible pair of document to compute the similarity can be very inefficient : given n documents, it requires n(n-1)/2 similarities to compute!!
**Locality Sensitive Hashing** is a family of techniques that allows to approximate the duplicate search, finding some *candidates*, so pairs of documents that are very probable to be duplicates.
Of course, as it happens in every approximation, there are *false positives* and *false negatives* rates that should be minimized and balanced among each other to obtain better results. This balancing is done by choosing the optimal values for the parameters *b* (number of bands) and *r* (number of rows for each band).

## Dataset
The dataset was previously scraped from Amazon; it contains the descriptions of computer products.

## Methodology
Duplicate search was performed following these steps:
1. **Shingling** : every description was transformed to a set of shingles, and each shingle was hashed.
2. **Min-wise Hashing** : using a minwise family of hash functions, each document represented as a set of shingles was transformed to a signature, applying the minwise hash.
3. **LSH** : each signature was splitted in b bands of r rows each. For each signature, each band was hashed to a different bucket array. All the document ids ending up in the same bucket for at least one bucket array are considered as *candidates*.

## Results
We compared both the ***efficiency*** and the ***effectiveness*** of our LSH implementation with the Naive Duplicate Search, that computes the Jaccard Similarity between every possible pair. 

Results show that the LSH implementation is obviously faster (0.0095 seconds against 0.8942 seconds), with an accuracy of 96,8 %.
