# SEARCH ENGINE WITH INVERTED INDEX FOR AMAZON COMPUTER RELATED PRODUCTS

## Dataset
The dataset contains product descriptions scraped from Amazon.it, regarding computers.
The preprocessing steps involved are:
1. TOKENIZATION, to get a list of words used in the description;
2. CLEANING, removing symbols; notice that we decided to keep not only alphabetic characters, but also
the numeric ones, because they may be very informative for our task (for example if you search for a 8 gb
ram computer, 8 is an important feature);
3. STOPWORDS REMOVAL, loading italian stop words and removing them from the list of tokens, because
they are not informative, just adding noise to the data;
4. STEMMING, to reduce the number of features and improve the effectiveness of the engine.

## Building the Inverted Index
In a vector space model, all the documents of the corpus are represented as vectors, such that each element is a Tf-Idf coefficient.
To build the index, we used a dictionary structure with multiple levels having format:
{’term1’ : { docID1:tf-idf(doc1)’, docID2:tf-idf(doc2)},
’term2’ ; { docID5:tf-idf(doc5)’}
}

## Query answering
In a vector space model, also the query has to be represented as a vector, but it’s not mandatory to use the same vectorization used for the corpus (but the preprocessing should be the same!). We decided to binary vectorize, keeping just a weight=1 if the term of the vocabulary appears in the query, and 0 otherwise. The
results are sorted by **Cosine similarity** score. Of course, the most relevant product is the first retrieved by the algorithm.
