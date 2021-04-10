---
title: "Data Cleaning"
author: Emily Zeng
date: 2021-01-20
categories:
  - blog
tags:
  - text-to-speech
---

The main dataset we'll use to start off with is [The Adventures of Tom Sawyer](https://librivox.org/tom-sawyer-by-mark-twain/) read by [John Greeman](https://librivox.org/reader/107).

Aeneas is the forced alignment software used. Follow setup instructions [here](https://github.com/readbeyond/aeneas/blob/master/wiki/INSTALL.md). Their Linux install script was useful for installing some requirements that were not mentioned, so check that out if the pip install fails.

I decided to use Aeneas's mplain format for easy word-level time detail. See the documentation [here](https://www.readbeyond.it/aeneas/docs/textfile.html#aeneas.textfile.TextFileFormat.MPLAIN). The main advantage this could offer is the ability to mix up the audio segment we are using at any point in the training session (aka start at various different points rather than some pre-defined start points). This would offer advantages in data augmentation.

Some notes with the plain text data:
- There's weird areas with double spaces - those were removed manually through search and replace
- some parts in the beginning and end are not included (eg. release date, etc.). Those are manually removed
- at the start of each audio recording, Greenman says a script along the lines of "this is a LibriVox recording..."
- He sometimes says the chapter name after each chapter number. The only exception seems to be chapter 1
- He sometimes says "end of chapter X" at the end of each chapter.
 
For the first 15 or so chapters, I manually looked through each instance and checked if he was actually saying them. After that, since he did for every chapter except for the first, I just added them directly.

There is also a need for preprocessing the roman numerals into numbers. Since that may be required during actual operation rather than just training, that got added to the preprocessing pipeline. There's a regex that searches for all valid roman numerals except for I and replaces it with numbers.

