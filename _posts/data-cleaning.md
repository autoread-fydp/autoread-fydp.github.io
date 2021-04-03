aeneas tested with creating subtitles file - basically all matches up. There are slight differences between the text itself and the spoken audio however:

- at the start of each audio recording, he says stuff about "this is a librivox recording..."
- He sometimes says the chapter name after each chapter number. Only exception seems to be chapter 1
- He sometimes says "end of chapter X" at the end of each chapter.
 
for the first 15 or so chapters, I manually looked through each instance and checked if he was actually saying them. After that, since he did for every chapter except for the first, I just added them directly.

There is also a need for preprocessing the roman numerals into numbers. Since that may be required during actual operation rather than just training, that got added to the preprocessing pipeline. There's a regex that searches for all valid roman numerals except for I and replaces it with numbers.

