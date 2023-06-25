# Deep Diving Into Neural Networks 

This is a repository where I delve deeper into the inner workings of neural networks and explore how they work in detail. Inspired from the great lectures by Andrej Karpathy. It also serves as a personal journal of my experimentations in machine learning. 

The repository contains several small projects, each having their own subfolder:



## [nanoGPT](https://github.com/hrdkbhatnagar/neural-networks-deep-dive/tree/main/nanoGPT)

An implementation of a medium sized Generatively Pretrained Transformer (GPT) in PyTorch. Inspired from OpenAI's GPT-2 language model, this is a character level language model. The text is encoded as a sequence and fed into a transformer (based on the ["Attention is all you need"]() paper), which then generates a probability distribution for the next character. The folder contains two notebooks:

- `00_nanoGPT_bigram_model`: Trying out character level encoding using just a bigram model and exploring the concept of self-attention
- `01_nanoGPT_training`: Extending the previous model with a transformer and scaling up the model to generate output 



When trained on Shakespeare's works, and training for about 15 minutes on a GTX 1070, it can generate texts like:

```
Yet see how the brook of it in my asure is hand:
I am doom too much death at years,
With the beauteous and Cominius;
Whom, which senses you with silly redic
So aught upon your try hands: yet your membeit
In Rome; but she bread'st not to your dagger
Advocation, so you must purposing with duty.

SLY:
Grandam, I see, to our honour.

First Senator:
Counsello.

Second Seest Citizen:
Measureless a knighman cried in Vienna
All.

First Senator:
Iffend the officer of her dishonour.
Or we meet us, ere it say in a town, Master
of Minius!
Wear it be, makes the haste; but one that we canot;
For the worst break not: to the Capitos.
```



## [Micrograd](https://github.com/hrdkbhatnagar/neural-networks-deep-dive/tree/main/micrograd)

A toy implementation for automatic diffrentiation and backpropagation written from scratch in Python in about 100 lines of code. Inspired from AutoGrad engine in Python, micrograd automatically computes gradients and creates a computational graph of the operations. It is built in a PyTorch-like API fashion. 



![](/Users/hardik/repos/neural-networks-deep-dive/micrograd/graphs/Digraph.gv.svg)



## [Makemore](https://github.com/hrdkbhatnagar/neural-networks-deep-dive/tree/main/makemore)

An autoregressive character level language model for "making more things". It takes one text file as an input and generates more things like that. For example, the `names.txt` dataset contains the most common American names is used as the training dataset. 

The complexity of makemore starts from a simple bigram model all the way to a Transformer model (like GPT) (*to be implemented soon!*). 

Currently the following models are implemented into makemore: 

- Bigram - where one character is used to predict the next one based on a lookup table 
- MLP  - based on [Bengio et. al 2003](https://www.jmlr.org/papers/volume3/bengio03a/bengio03a.pdf) 
- Wavenet - based on [Aaron van den Oord et. al 2016](https://arxiv.org/abs/1609.03499)

When trained on the names dataset, containing entries like:

```
Emma
Olivia
Ava
Isabella
Sophia
Charlotte
Mia
Amelia
Harper
Evelyn
```

It currently can generate unique names such as: 

```
Tokore
Yohna
Nichira
Hayleigh
Brakel
Shyvan
Luna
Aleysh
Kelon
Luwa
Archan
Jennesty
Brarai
```



Along the way, there are several nice explorations done into training deep networks and their working under the hood. 

![activation_graph](https://raw.githubusercontent.com/hrdkbhatnagar/neural-networks-deep-dive/main/images/makemore_activations_graph.png?token=GHSAT0AAAAAAB5LO6ZGH7CRFRWZNVLH6226ZEN7SAQ)

![update_ratio_graph](https://raw.githubusercontent.com/hrdkbhatnagar/neural-networks-deep-dive/main/images/makemore_update_ratio_graph.png?token=GHSAT0AAAAAAB5LO6ZHRPEQSDXESYP2NQE4ZEN7UAQ)

## Environment 

This project enviroment was created using Conda. The entire environment required for this project is described in the ``environment.yml`` located in the main directory.  The enviroment can be recreated using:

```bash
$ conda env create --name torch --file environment.yml
```