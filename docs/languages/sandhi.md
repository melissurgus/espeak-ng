# Tone sandhi

## How to implement tone sandhi: 3 (and a half) ways

### 1: via intonation

As implemented in Mandarin, Hakka, & Vietnamese, by altering the intonation.c file. The snag here is getting the code to work, particularly for the tone numbers. Perhaps the answer is in the "tone language" option in tr_languages.c.

### 2: via spelling rules

As implemented in Cherokee; by using the text substitutions in the language rules file. This currently works acceptably-- but only within word boundaries. (As most sandhi occurs across boundaries, this is not ideal.) The problem is the dictionary file, where characters are treated as "words," replaced with their pronunciation from the dictionary and translated into phonemes one by one. If we could either persuade the dictionary that characters are not words, or persuade it to replace all characters in a phrase before translating them into phonemes, this fix might work. Would that be in dictionary.c?

### 3: via phonetics/phonology interface

A better solution from a linguistic perspective, though not yet implemented: encode the tones as phonemes whose realization depends on context. This would require a "next tone" function (parallel to the "next phoneme" functions already in existence) in compiledata.c. I don't know how to do this.
