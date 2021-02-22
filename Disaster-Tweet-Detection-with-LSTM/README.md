# DISASTER-RELATED TWEETS DETECTION : COMPARING BERT AND A CUSTOM LSTM

## Introduction
Twitter's ubiquity and real time nature make it a very powerful source to enhance emergency situation awareness. As soon as something happens (earthquakes, storms,..) people start to post about it, providing important information to crisis management organization. This is why it is very important to have a trained model that is able to raise alarms when a disaster-related tweet is detected. The stream is indeed full of irrelevant data, and this kind of filtering is strictly required to detect natural disaster events around the world.

## Dataset
The dataset used to build the classifier is available on Kaggle (see the references).

## Methodology
After preprocessing, we used PyTorch to build a very easy LSTM-based neural network with an Embedding layer, because they are known to be good for text classification tasks.
We compared the results obtained with our network with the ones obtained by applying Transfer Learning on BERT network, built by Google. Results and details about the experimentation are described in the report file of this repository folder.

## References
Dataset : https://www.kaggle.com/vstepanenko/disaster-tweets

Short tutorial on Transfer Learning with BERT : https://github.com/nlptown/nlp-notebooks/blob/master/Text%20classification%20with%20BERT%20in%20PyTorch.ipynb
