---
title: "New Dataset"
author: Emily Zeng
date: 2021-03-02
categories:
  - blog
tags:
  - text-to-speech
---

I investigated the previous preprocessing pipeline and there didn't seem to be any issues. However, just in case, I decided to switch to using the mel spectrogram generation code in the original pipeline. The biggest issue is likely on the data side.

The biggest change is likely switching to use a new dataset. The Adventures of Tom Sawyer is relatively short and is read by a male voice. A female voice may be easier for transfer learning later if I retrain a model using the LJSpeech dataset. I settled on using the voice of [Karen Savage](https://librivox.org/reader/103) after digging around for lists of the "best narrators on LibriVox". She happens to narrate multiple books in the Anne of Green Gables series. Since those books all happen to be in the same series, it's likely safe to use all four books in my dataset. Those four books are:
- [Anne of Avonlea](https://librivox.org/anne-of-avonlea-by-lucy-maud-montgomery-2/)
- [Anne of Green Gables](https://librivox.org/anne-of-green-gables-by-lucy-maud-montgomery-3/)
- [Anne of the Island](https://librivox.org/anne-of-the-island-by-lucy-maud-montgomery-2/)
- [Anne's House of Dreams](https://librivox.org/annes-house-of-dreams-by-lucy-maud-montgomery-version-2/)

The tensorboard results for the text2mel model can be found [here](https://tensorboard.dev/experiment/rDgXsZeQRAa7HASRtBup6w/#scalars). An additional SSRN model was also trained and can be seen [here](https://tensorboard.dev/experiment/rj6h6BCqRO2T9f9oJtPkMA/#scalars)

This text2mel model seems to be overfitting at the 50k step mark, and also does not produce sound. The SSRN model works perfectly fine with the pre-trained text2mel model however, meaning the issue is on the text2mel side.