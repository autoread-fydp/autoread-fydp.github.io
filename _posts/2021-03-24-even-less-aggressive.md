---
title: "even less aggressive silence filtering and more data"
author: Emily Zeng
date: 2021-03-24
categories:
  - blog
tags:
  - text-to-speech
  - audio-samples
---

Tensorboard data can be found [here](https://tensorboard.dev/experiment/L7nvx6uGTgqabdQB934lLw/). This version used even less aggressive silence filtering (set to aggressiveness value to 0 this time) as well as data from two additional books in the anne of green gables series:

- [Rainbow Valley](https://librivox.org/rainbow-valley-version-2-by-lucy-maud-montgomery/)
- [Rilla of Ingleside](https://librivox.org/rilla-of-ingleside-by-lucy-maud-montgomery/)

I had originally missed those books since they didn't start with "Anne"

This model is definitely an improvement from the previous one, being much more consistent in its output. It is also more sensitive to punctuation, comparitively.

The best example of this model at work is probably its attempt at reading a page from Harry Potter and the Order of the Phoenix as part of the entire autoread system (camera and ocr included).

<audio
    controls
    src="/assets/audio/ksavage-6/hp-page.wav">
    Your browser does not support the
    <code>audio</code> element.
</audio>

# More audio samples

<figure>
  <figcaption>The birch canoe slid on the smooth planks.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/0.wav">
        Your browser does not support the
        <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Glue the sheet to the dark blue background.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/1.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>It's easy to tell the depth of a well.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/2.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>These days a chicken leg is a rare dish.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/3.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Rice is often served in round bowls.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/4.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>The juice of lemons makes fine punch.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/5.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>The box was thrown beside the parked truck.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/6.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>The hogs were fed chopped corn and garbage.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/7.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Four hours of steady work faced us.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/8.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>Large size in stockings is hard to sell.</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/9.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>

<figure>
  <figcaption>however creating audiobooks can be expensive</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/100.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>
<figure>
  <figcaption>however, creating audiobooks can be expensive</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/101.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>
<figure>
  <figcaption>however, creating audiobooks can be expensive!</figcaption>
  <audio
      controls
      src="/assets/audio/ksavage-6/102.wav">
          Your browser does not support the
          <code>audio</code> element.
  </audio>
</figure>