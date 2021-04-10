---
title: "`webrtcvad` and Shorter Sections"
author: Emily Zeng
date: 2021-03-15
categories:
  - blog
tags:
  - text-to-speech
---

Cheryl and I spent some time taking a bit of a break from training models to try and figure out what it is. One big thing could be an issue with long sentences. When digging around on some forums, we found that some people are having problems with their custom datasets when longer sentences keep popping up. 

Because manually labelled data is entirely unfeasible for this project, not to mention takes away from the spirit of "mostly automatically generated dataset", I decided to also lookup good ways to cut off the silence at the start of audio segments. [`webrtcvad`](https://github.com/wiseman/py-webrtcvad) looked like the most promising option as I was unable to configure Aeneas to do it automatically. I also did not have as much luck with other forced alignment programs, so `webrtcvad` it is.

Attempt 1 at removing starting silence and breath intake can be found [here](https://tensorboard.dev/experiment/RgvF1VynQsyqul8wV5pm3g/). A second try filtered out audio segments that were longer than 10 seconds can be found [here](https://tensorboard.dev/experiment/xc5NjphxRAanGkdU1kQbpA/)

Other modifications include: 
- added breaking up segments using -- in preprocessing
    - made sure to filter out stuttering
- increased minimum length of each segment to 5 words
- manual efforts to remove overly short segments
- filtered single word before comma --> added to next fragment
- previous attempts at filtering . . . found to be faulty --> fixed

notes: 
- some abbreviations still treated as the end of a sentence
    - this is from `nltk punkt`, can't really do much beyond manual fixing when I see it

# Audio Samples

The first run was actually very weird. I ran it through the harvard sentences again, and while most sentences remained entirely silent, it would randomly start speaking sometimes from the middle of the sentence. I have included those examples below:

<figure>
  <figcaption>Glue the sheet to the dark blue background.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-4/1.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>
<figure>
  <figcaption>however creating audiobooks can be expensive.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-4/100.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

The training run with that filtered out sentences longer than 10 seconds also had the same issue, but different sentences produced sound now. An example is found below:

<figure>
  <figcaption>The birch canoe slid on the smooth planks.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-4-2/0.wav">
        Your browser does not support the
        <code>audio</code> element.
  </audio>
</figure>

It's possible that I have been too aggressive in removing silences.