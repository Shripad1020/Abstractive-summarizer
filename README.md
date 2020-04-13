## Dependencies

* [Tensorflow](https://www.tensorflow.org/versions/r0.10/get_started/os_setup.html) or [Theano](http://deeplearning.net/software/theano/install.html)
* Keras 
* python-Levenshtein (pip install python-levenshtein)

Use [pip](https://pypi.python.org/pypi/pip) to install any missing dependencies.

## Basic Usage

### Data

Once you have the data ready save it in a python pickle file as a tuple:
`(heads, descs, keywords)` were `heads` is a list of all the head strings,
`descs` is a list of all the article strings in the same order and length as `heads`.
I ignore the `keywrods` information so you can place `None`.

[Here](http://opendata.stackexchange.com/questions/4981/dataset-of-major-newspapers-content) is a link on how to get similar datasets

### Build a vocabulary of words
The [vocabulary-embedding](./vocabulary-embedding.ipynb)
notebook describes how a dictionary is built for the tokens and how
an initial embedding matrix is built from [GloVe](http://nlp.stanford.edu/projects/glove/).

### Train a model
The [train](./train.ipynb) notebook describes how a model is trained on the data using [Keras](http://keras.io/).

### Use model to generate new headlines
The [predict](./predict.ipynb) notebook generate headlines by the trained model and
showes the attention weights used to pick words from the description.
The text generation includes a feature which was
not described in the original paper, it allows for words that are outside
the training vocabulary to be copied from the description to the generated headline.

## Examples of headlines generated
Good (cherry-picked) examples of headlines generated:
![cherry picking of generated headlines](./cherry_picking.png)
![cherry picking of generated headlines](./cherry_picking1.png)

## Examples of attention weights
![attention weights](./attention_weights.png)
