# Sentiment analysis with recurrent neural networks ( RNN )

Emotion recognition project using IMDB dataset and PyTorch library. In this project, the neural network is trained to be able to recognize emotions in a text.

### The overall structure of the project:

1. Installation of required libraries for the project:
    * PyTorch -> for For neural network architecture design and training. 
    * torchtext -> For loading the IMDB database and creating a dictionary and other tasks
    * spacy -> To tokenize the words in the sentence

    ```
    pip install pytorch torchtext===0.6.0 spacy
    ```
    [install PyTorch for Cuda or other OS](https://pytorch.org/get-started/locally/)

2. Load the IMDB dataset and create a dictionary and prepare the data for neural network training:
    * Load tokenizer and create dictionary fields.
    * Download dataset using dictionary and tokenizer fields.
    * Separation of train and validation and test data.
    * Create a dictionary of words.
    * Batching of data for neural network training.

3. Neural network architecture design:
    * Embedding layer -> This layer is to make the sentence structure easier for the network. ***which has an input equal to the number of dictionary words with an output.***
    * RNN layer -> An RNN layer for sentence processing, which has an input and an output equal to the output of the embedding layer.
    * Fully connected or Linear layer -> This layer has the same input as the output of the RNN layer and outputs as many classes as desired. This layer is used to convert the RNN layer vector to the desired output.

### The structure of the RNN network:
![RNN](assetes/rnn.png)
The vector that enters the RNN network is the size of the number of dictionary words. When a sentence enters the network, it is not the words that enter the network, but the weights and numbers of the words in the dictionary that enters the network.

The RNN network remains like a chain. where words are processed. The words of the sentence that enter the network are interdependent and affect each other. If you look carefully in the photo, you can see that the parts of the network are connected and not a separate part. All the words in the sentence are related.

Recursive networks are suitable for processing text and audio that have dependencies. One of the weak points in this neural network is that it is not very accurate in long sentences.

It is better to use LSTM network to process long sentences. That network has a separate memory in its heart, which greatly increases the accuracy of the network.

[Long short-term memory (LSTM)](https://github.com/Eiliya-Zanganeh/Advanced-Sentiment-Analysis-Long-Short-Term-Memory-LSTM)

Other techniques can also be used to increase the accuracy of the model. For example, using the glove language model to create a partition.

[Using techniques to increase network accuracy](https://github.com/Eiliya-Zanganeh/Advanced-Sentiment-Analysis-Long-Short-Term-Memory-LSTM)

4. Selection of loss function and optimizer and neural network training:
    * Load loss function BCEWithLogitsLoss and Stochastic gradient descent optimizer.
    * Network training with batches of training data and updating network weights with loss function and optimizer.
    * Evaluate the network in each epoch and find the value of loss and accuracy.
    * Final test of the model and save it.

Produced by [Eiliya Zanganeh](https://github.com/Eiliya-Zanganeh)