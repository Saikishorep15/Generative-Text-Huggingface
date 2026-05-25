Introduction
In recent years, there has been an increasing interest in open-ended language generation thanks to the rise of large transformer-based language models trained on millions of webpages, including OpenAI's ChatGPT and Meta's LLaMA. The results on conditioned open-ended language generation are impressive, having shown to generalize to new tasks, handle code, or take non-text data as input. Besides the improved transformer architecture and massive unsupervised training data, better decoding methods have also played an important role.

This blog post gives a brief overview of different decoding strategies and more importantly shows how you can implement them with very little effort using the popular transformers library!

All of the following functionalities can be used for auto-regressive language generation (here a refresher). In short, auto-regressive language generation is based on the assumption that the probability distribution of a word sequence can be decomposed into the product of conditional next word distributions:


We will give a tour of the currently most prominent decoding methods, mainly Greedy search, Beam search, and Sampling.

Let's quickly install transformers and load the model. We will use GPT2 in PyTorch for demonstration, but the API is 1-to-1 the same for TensorFlow and JAX.
