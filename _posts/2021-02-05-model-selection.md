---
title: "Model Selection"
date: 2021-02-05
categories:
  - blog
tags:
  - text-to-speech
---

The original plan was to train first with [flowtron](https://arxiv.org/abs/2005.05957) since it offers multi-voice training. However, the data for that would be more difficult to gather as it requires labels for the identity of the current narrator, as well as many more narrators. Instead, we will first try training with the single speaker models.

The first single speaker model we were originally going to start off with was [tacotron2](https://arxiv.org/pdf/1712.05884.pdf), and use transfer learning to fit it to our dataset. However, after looking more closely through their processing code for the online pre-trained model, it does not include quotation marks in its list of allowed symbols (see [this file on their github](https://github.com/NVIDIA/tacotron2/blob/master/text/symbols.py))

Quotation marks were probably unnecessary for their use case, but in the case of fiction novels, it is relatively important for determining the switch between dramatic narration versus more conversational speech. This lack of quotation marks means that we will need to train from scratch if we use tacotron, and my 2080ti is almost definitely not good enough to train multiple iterations of tacotron within the time limitations of this project.

Instead, we will go with the more lightweight text2mel model, as described in [Efficiently trainable text-to-speech system based on deep convolutional networks and guided attention](https://arxiv.org/abs/1710.08969). The use of no recurrent layers (CNN only) makes computation during training more parallelizable and guided attention is also supposed to speed along the training process. Most importantly, the paper specifically mentions being able to train the entire thing on only two GTX980 Ti GPUs and took only about 15 hours for 340K training iterations. My 2080 Ti should be much better than those, and this would give me a lot more room to play with my dataset, which is likely to be the real issue here. 

The paper also goes over their SSRN (spectrogram super-resolution network), which is responsible for turning mel spectrograms into full-resolution spectrograms. This portion can be replaced by melGAN later if we have time, but using SSRN for now also seems like a good time-saving method for experimenting

The allowed characters in the pre-trained network are also insufficient here, consisting of only `abcdefghijklmnopqrstuvwxyz'.?`. In this case, however, training the model from scratch will not be an issue.
