---
layout: post
title: "Automatic Speech Recognition for Indigenous Languages"
date: 2019-11-03
---

# Introduction

Recently, I've begun work on automatic speech recognition for a First Nations
people.
It's an incredibly exciting opportunity, because this is one of the
reasons I became interested in deep learning.
The idea is to build a speech-to-text (STT) system to facilitate transcription
and to help their language revitalization efforts.
I am also hoping that we can complete a one-week coding/machine learning boot
camp for the younger members of the tribe.

There is also a need to complete this project quickly, because there are less
than 200 fluent speakers today.
It also provides some interesting challenges, because much of the research
around ASR has been devoted to English.
Our plan is to incorporate as much of the current research as possible into our
machine learning model.

I and other team members think of this as a first step.
We plan on using the lessons learned on this project to streamline the process
to bring it to other Indigenous people.
And we'd like to create a network of indigenous deep learning practitioners.
We are hoping that this can become a national, then international project.
It's a huge goal, but I think we can accomplish it some day.

# Model

Our first model will be the Baidu Research's [Deep Speech][1] model.
There is another Indigenous ASR effort that has used that model to excellent
effect.
Mozilla has turned the Deep Speech model into a [ASR library][2].
We intend to use this as our baseline model.

The Deep Speech model requires three types of data:
1. audio converted to mel frequency cepstral coefficients (MFCC);
2. corresponding transcriptions that are time-aligned to the audio (e.g. if the
   utterance "I like pizzas." begins at 53s and ends at 56s in the recording, then   the transcription will have 53s and 56s associated to "I like pizzas.";
3. a text corpus.
The model takes sequences of vectors (audio segments converted to MFCC vectors)
and outputs sequences from an alphabet.
The loss is connectionist temporal classification (CTC), which is based on the
argmax of $p(l \mid x)$, where $l$ is a sequence of characters from the
alphabet augmented with a blank character and $x$ is the sequence of vectors
coming from the audio.
The model is an bi-directional RNN (although, the Mozilla library uses a
bi-directional LSTM) with the following architecture: three fully connected
layers, followed by a bi-directional RNN layer, with a fifth fully connected
layer and softmax output.

We also train a language model to correct any possibly phonetically correct
transcriptions that are not correct.
The authors of the Deep Speech paper give these examples:

| RNN output | Decoded Translation |
| --------|-------- |
| what is the weather like in bostin right now | what is the weather like in boston right now |
| prime miniter nerenr modi | prime minister narendra modi |
| arther n tickets for the game | are there any tickets for the game |

The model is relatively simple, especially compared to the massive language
models out today, but given the fact that we do not have tens of thousands of
hours of transcribed audio, I think this will be for the best.

After this, we will start experimenting with different models and techniques.
There are about eight papers that I am interested in exploring further, to see if
they're a good fit for our project:
- [Deep Speech 2][3] (which adds convolutional layers and more RNN layers);
- [Exploring Neural Transducers for End-to-End Speech Recognition][4] (the
  paper claims that RNN-transducers are better for sequence-to-sequence tasks);
- [wav2vec: Unsupervised Pre-Training for Speech Recognition][5] (in a manner
  analogous to word2vec, the audio files are sent through a transformer);
- [Who Needs Words? Lexicon-Free Speech Recognition][6] (they use a
  character-based LM with a gated CNN, this might not be useful, because they
  are trained on much larger amounts of text data than we will have on hand);
- [SpecAugment: A Simple Data Augmentation Method for Automatic Speech Recognition][6]
(the paper presents multiple methods for augmenting the audio data, which will
be important for us, due to our data-set size);
- [Sequence-to-Sequence Speech Recognition with Time-Depth Separable
  Convolutions][7] (their model has a better word error rate (WER) on the
  LibriSpeech data-set and its convolutional nature means the model is more
  parallelizable than RNN models);
- [Accelerating Deep Learning by Focusing on the Biggest Losers][8]
  (selective-backprop skips the calculation of the gradient if the loss is
  small enough, the models are trained to a comparable accuracy and the
  training is significantly sped-up, this would be great for us, because our
  computational resources are limited);
- [Lightweight and Efficient End-to-End Speech Recognition Using Low-Rank
  Transformer][9] (the upside of the transformer is its highly parallelizable
  nature, the downside is its size requires much more computational power; this
  paper attempts to make a more computationally efficient transformer with
  comparable error rates);
- [Gradient Descent: The Ultimate Optimizer][10] (this paper proposes attaching
  the hyperparameters to the directed acyclic graph (DAG) used to calculate the
  gradients, this means that you have hyperparameters to tune your
  hyperparameters, but you just attach your new hyperparameters to the DAG;
  fortunately, you don't have to add ad infinitum, but maybe go to a depth of
  three layers of hyperparameters attached to the DAG).

# Data

The biggest lesson, so far, is how much effort is devoted to data acquisition
and cleaning.
Currently, there is probably 15 hours of time-aligned transcribed audio,
although there is more audio available.
We have a number of hurdles to overcome:
1. we have to get permission to use the other audio from various organizations;
1. we have to check the audio quality;
1. we have to check the transcription quality;
1. the transcriptions are in differing orthographies;
1. we have to create transcriptions;
1. we have to obtain permission for various texts, to use in our language model;
1. we have to convert some of the texts to utf-8 text.

We are now in data pre-processing stage and data collection stage.
The one good thing about not having enough data yet, is the ability to set data
quality standards ahead of time.
This will save a lot of time on our engineering efforts.

We're confident that most of these challenges can be overcome with a robust
software engineering approach.

# Final Thoughts

As I said, I'm very excited for this project.
I think it can be the start of something amazing for the community.
I would love to see what other communities can do with this technology.
Will it be incorporated into art, storytelling, more efficient government?
Can we begin to rebuild the knowledge and culture that was taken from us?
I don't know, but I want to work as hard as possible to make the answer yes.

[1]: https://arxiv.org/abs/1412.5567
[2]: https://github.com/mozilla/DeepSpeech
[3]: https://arxiv.org/abs/1512.02595v1
[4]: https://arxiv.org/abs/1707.07413
[5]: https://arxiv.org/abs/1904.05862v4
[6]: https://arxiv.org/abs/1904.04479v4
[7]: https://arxiv.org/abs/1904.08779v2
[8]: https://arxiv.org/abs/1910.00762v1
[9]: https://arxiv.org/abs/1910.13923v1
[10]: https://arxiv.org/abs/1909.13371v1
