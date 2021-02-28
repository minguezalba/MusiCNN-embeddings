# MusiCNN-embeddings


The project consists on evaluating music similarity and building a genre classifier using song embeddings from GTZAN dataset extracted with Essentia’s MSD-MusiCNN model.

The repository is divided in three different notebooks or modules:

## 1. Dataset generation
In this notebook, we will do all the necessary tasks to build a songs-embedding dataset from the GTZAN dataset in order to use it in several tasks: evaluating songs similarity and genre classification.

The steps are the following:
- **Download GTZAN dataset** with the help of mirdata library.
- **Download Essentia’s MSD-MusiCNN TensorFlow model** for the specific task of genre classification.
- **Embeddings extraction**: Extract songs-temporal embeddings using MusiCNN model and process them to get mean-embeddings.
- **Labels processing**: Encode genre labels to numeric values.
- **Save data** to npy files to use them in the following tasks.

## 2. Music similarity
In this notebook, we will **evaluate music similarity** based on previously extracted songs embeddings. Each song embedding in the dataset has a single ground-truth genre label associated. We will assume these genres as a proxy for evaluating similarity, that is, considering two songs are similar when they have the same genre label. Evaluation metrics such as average precision@10, MAP@10, and MAP@50 will be computed across the entire dataset

## 3. Genre classification
In this notebook, we will **train and evaluate a new transfer learning classifier** using the embeddings from GTZAN dataset, extracted by Essentia’s MSD-MusiCNN TensorFlow.
We will use the audio features (embeddings) as an input to train a shallow target classifier inspired by the ones used in *Alonso-Jiménez, P., Bogdanov, D., & Serra, X. (2020). Deep embeddings with Essentia models*: a multilayer perceptron with a single hidden layer with 100 neurons and ReLU activations. The output layer uses softmax for predictions.
To do this task, we will use **Pytorch**.


## Usage
No package installation is required. You can run all the notebooks directly in Google Colab with the link located on top of each notebook.

---
Author: Alba Mínguez Sánchez

March 2021
