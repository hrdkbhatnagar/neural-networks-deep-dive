# Deep Diving Into Neural Networks 

This is a repository where I delve deeper into the inner workings of neural networks and explore how they work in detail. Inspired from the great lectures by Andrej Karpathy. It also serves as a personal journal of my experimentations in machine learning. 

The repository contains several small projects, each having their own subfolder:



## [Micrograd](https://github.com/hrdkbhatnagar/neural-networks-deep-dive/tree/main/micrograd)

A toy implementation for automatic diffrentiation and backpropagation written from scratch in Python in about 100 lines of code. Inspired from AutoGrad engine in Python, micrograd automatically computes gradients and creates a computational graph of the operations. It is built in a PyTorch-like API fashion. 

​	

## [Makemore](https://github.com/hrdkbhatnagar/neural-networks-deep-dive/tree/main/makemore)

A character level language model for "making more things". It takes one text file as an input and generates more things like that. For example, the `names.txt` dataset contains the most common American names is used as the training dataset. 

The complexity of makemore starts from a simple bigram model all the way to a Transformer model (like GPT) (*to be implemented soon!*). Along the way, there are several nice explorations done into training deep networks and their working under the hood. 

Currently the following models are implemented into makemore: 

- Bigram - where one character is used to predict the next one based on a lookup table 

- MLP  - based on [Bengio et. al 2003](https://www.jmlr.org/papers/volume3/bengio03a/bengio03a.pdf) 

  



## Environment 

This project enviroment was created using Conda. The entire environment required for this project is described in the ``environment.yml`` located in the main directory.  The enviroment can be recreated using:

```bash
$ conda env create --name torch --file environment.yml
```



