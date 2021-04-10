---
title: "less aggressive silence filtering"
author: Emily Zeng
date: 2021-03-20
categories:
  - blog
tags:
  - text-to-speech
  - audio-samples
---

I modified the aggressiveness from 3 to 1. Training history can be found [here](https://tensorboard.dev/experiment/I53q9i7JToOXJN4W85fZag/) for a run which used the LJSpeech mode I trained, and [here](https://tensorboard.dev/experiment/kqrfbku1QtmDpny01hjCBQ/) for a model trained from scratch. These models are actually starting to consistently read out words. Interestingly enough, the model trained from scratch actually seems to be performing better.

Unfortunately, the model doesn't seem to be differentiating much between punctuations

# Transfer learned model

<figure>
  <figcaption>The birch canoe slid on the smooth planks.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/0.wav">
        Your browser does not support the
        <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Glue the sheet to the dark blue background.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/1.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>It's easy to tell the depth of a well.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/2.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>These days a chicken leg is a rare dish.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/3.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Rice is often served in round bowls.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/4.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>The juice of lemons makes fine punch.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/5.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>The box was thrown beside the parked truck.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/6.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>The hogs were fed chopped corn and garbage.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/7.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Four hours of steady work faced us.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/8.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Large size in stockings is hard to sell.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/9.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>however creating audiobooks can be expensive</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/100.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>
<figure>
  <figcaption>however, creating audiobooks can be expensive</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/101.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>
<figure>
  <figcaption>however, creating audiobooks can be expensive!</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5/102.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

# Model from scratch

<figure>
  <figcaption>The birch canoe slid on the smooth planks.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/0.wav">
        Your browser does not support the
        <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Glue the sheet to the dark blue background.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/1.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>It's easy to tell the depth of a well.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/2.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>These days a chicken leg is a rare dish.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/3.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Rice is often served in round bowls.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/4.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>The juice of lemons makes fine punch.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/5.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>The box was thrown beside the parked truck.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/6.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>The hogs were fed chopped corn and garbage.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/7.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Four hours of steady work faced us.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/8.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Large size in stockings is hard to sell.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/9.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>however creating audiobooks can be expensive</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/100.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>
<figure>
  <figcaption>however, creating audiobooks can be expensive</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/101.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>
<figure>
  <figcaption>however, creating audiobooks can be expensive!</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-5-1/102.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>
