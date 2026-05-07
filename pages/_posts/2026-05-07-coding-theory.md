---
title: "Coding Theory: A Playful Introduction"
description: "Let's cut through the noise, one bit at a time"
categories: [Math]
tags: [math, sos]
math: true
date: 2026-05-07 16:20 +0530
---
[Introduction](#introduction) is after the below thought experiment.

## Codes for Communication
### A Problem
Imagine you are a 10 year old child in 1900s, you want to talk with your best friend at late night who is also your opposite neighbour. you dont want to disturb others (or perhaps wanna talk in secret), so you try speaking softly but the distance is too long to reach them, thankfully you both can see each other from your bedroom windows. the question is how will you two communicate? you each have a flashlight 🔦 that you can use. Think about it!

### Attempt 1 (Drawing)
Well ofcourse, you turn ON your flashlight and start drawing letters, you create the shape of $$\textrm{I}$$ with one single vertical stroke of your flashlight and then your friend can see the line and understand it. then you start drawing $$\textrm{L}$$ with one vertical stroke and an horizontal stroke below it from where you ended and realise that it will look as <span style="display:inline-block; transform: scaleX(-1);">
  $\textrm{L}$
</span> to your friend, so you need to draw <span style="display:inline-block; transform: scaleX(-1);">
  $\textrm{L}$
</span> then your friend interprets it correctly as $$\textrm{L}$$. then you draw an oval $$\textrm{O}$$ but wonder what if its interpreted as $$\textrm{0}$$, then you send $$\textrm{V}$$ with two simple storkes, then when you send <span style="display:inline-block; transform: scaleX(-1);">
  $\textrm{E}$
</span> you soon realise a bigger problem, interpreting symbols with many strokes isn't easy afterall the old strokes dont stay in the air until you finish the letter. So you wanted to do something more _precise_.

### Attempt 2 (Blinking)
till now, your flashlight was always ON, you realise you havent turned it OFF since you started and then it clicks, what if you tried blinking (turning your flashlight ON and then OFF). To keep it simple, you _assign_ $$\textrm{A}$$ as $$1$$ blink, $$\textrm{B}$$ as $$2$$ blinks, and so on $$\textrm{Z}$$ as $$26$$ blinks. This works! 
To send $$\textrm{I LOVE}$$, you first blink your flashlight $$9$$ times then wait for some time and blink it $$12, 15, 22$$ and $$5$$ times. Your friend counts the number of blinks ($$\#$$blinks) and computes the letter sent. Ofcourse, you need to make sure there is sufficient pauses between blinks, otherwise $$\textrm{I L}$$ can be interpreted as $$\textrm{U}$$ with $$9+12=21$$ blinks. also, you will need different pauses between $$\textrm{I}$$ and $$\textrm{L}$$ and $$\textrm{L}$$ and $$\textrm{O}$$ as one separates words and one separates letters of same word. Now $$\textrm{I LOVE}$$ is $$9+12+15+22+5=63$$ blinks, and it gets the job done. We can do better, but first celebrate as you have just discovered Coding Theory.

### Introduction
What you developed was a _code_, i.e., a system for transferring _information_ (in this case among people). This code helped you communicate the _message_ (something to be sent) by converting it into a _codeword_ (something that's actually sent). When you were converting a letter into $$\#$$blinks, you were _encoding_ and your friend was _decoding_ when they were converting $$\#$$blinks back into the letter. _Coding Theory_ is the study of such codes.
> This shouldn't be confused with the popular term with the same name 'coding' which means writing a computer program i.e., instructions for a computer.
{: .prompt-warning}

Now, let's back to the problem.
### Attempt 3 (Frequency Analysis)
This discovery is great and as a result you want to send $$\textrm{I LOVE CODING THEORY}$$ next, well guess what, it turns out to be $$206$$ blinks, too long :(

But then, here you find your first breakthrough, you realise there is no need to map $$\textrm{A$-$Z}$$ to $$\textrm{1$-$26}$$ sequentially. From your futuristic experience of Scrabble, you know that letter $$\textrm{E}$$ comes up the most in english langauge, so why not assign it $$1$$ blink instead of $$5$$. and we can go ahead and assign second most frequent letter of the alphabet $$\textrm{T}$$ as $$2$$ blinks, to the third most frequent $$\textrm{A}$$ as $$3$$ blinks, and so on until the least frequent $$\textrm{Q}$$ and $$\textrm{Z}$$ as $$25$$ and $$26$$ blinks respectively, this ensures that we use fewer blinks for popular letters and hence can send our message faster.

Below table, gives an idea of frequency of each letter. Convince yourself that for any two pair of letters, it is better to represent the more frequent letter with lesser blink to minimise the _expected_ total number of blinks.

<p><a href="https://upload.wikimedia.org/wikipedia/commons/d/d5/English_letter_frequency_%28alphabetic%29.svg" class="popup img-link light shimmer" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/d/d5/English_letter_frequency_%28alphabetic%29.svg" alt="English letter frequency (alphabetic)" loading="lazy"></a>
<a href="https://upload.wikimedia.org/wikipedia/commons/d/d5/English_letter_frequency_%28alphabetic%29.svg" class="popup img-link dark shimmer" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/d/d5/English_letter_frequency_%28alphabetic%29.svg" alt="English letter frequency (alphabetic)" loading="lazy" style="filter: invert(100%) brightness(80%);"></a>
<em>Frequency Analysis ($\%$) of English letters</em></p>

Using this, $$\textrm{I LOVE CODING THEORY}$$ is shortened to $$138$$ blinks, a whopping $$33\%$$ reduction!
### Punctuation
Before optimising our code further, let's discuss the important topic of punctuation. When we are sending our blinks, there are actually three levels of _pauses_ that we need to take between blinks for accurate decoding, these are
- pauses between blinks of same letter
- pauses between blinks of different letters
- pauses between blinks of different words

The technical term for these pauses is punctuation and it has been an important part of our codes till now.
### Attempt 4 (Morse Code)
Let's try to formalise our previous system. Instead of writing blinks over and over again, we can use codewords to represent our message, so $$\textrm{A}$$ means $$\boldsymbol{\cdot}$$, $$\textrm{B}$$ means $$\boldsymbol{\cdot}\boldsymbol{\cdot}$$, $$\textrm{C}$$ means $$\boldsymbol{\cdot}\boldsymbol{\cdot}\boldsymbol{\cdot}$$, and so on. This is essentially Base $$1$$ system of counting. Where, we literally have same number of $$\boldsymbol{\cdot}$$'s (the length of the codeword) as number of blinks, akin to how ancient people used number of sticks to count their number of sheeps. 

> Notice that in this way, both our message and the corresponding codeword can be represented by different sets of symbols, for our message the symbols are the alphabets whereas for the codeword, the symbols are the dots.

Here, we were using only one symbol $$\boldsymbol{\cdot}$$, but what if we use two symbols instead? That's Base $$2!$$ With two symbols (say $$\boldsymbol{\cdot}$$ and $$-$$) the possibilities explode, initially we had one codeword for every length, now there are $$2^n$$ codewords with length $$n$$, for eg, for length $$2$$, possible codewords are $$\boldsymbol{\cdot}\boldsymbol{\cdot}$$, $$\boldsymbol{\cdot}-$$, $$-\boldsymbol{\cdot}$$ and $$--$$. As, we now have many more codewords of short length, this will again shorten the _average_ length of the codewords and in turn, hopefully reduce $$\#$$blinks. But, what does the symbols $$\boldsymbol{\cdot}$$ and $$-$$ represent here? Well, in Morse Code, people denote $$\boldsymbol{\cdot}$$ by a short blink (dot) and $$-$$ by long blink (dash), in particular, a blink in a dash is __three times as long as__ a dot. Here, every letter of the alphabet can be written as a codeword comprised of dots and dashes as shown in below table

<p><a href="https://paramrathour.github.io/website-assets/morse-code-encoding.png" class="popup img-link light shimmer" target="_blank"><img src="https://paramrathour.github.io/website-assets/morse-code-encoding.png" alt="Morse Code (encoding)" loading="lazy"></a>
<a href="https://paramrathour.github.io/website-assets/morse-code-encoding.png" class="popup img-link dark shimmer" target="_blank"><img src="https://paramrathour.github.io/website-assets/morse-code-encoding.png" alt="Morse Code (encoding)" loading="lazy" style="filter: invert(100%) brightness(80%);"></a>
<em>Morse Code Encoding for English letters</em></p>

Notice again that $$\textrm{E}$$ is just a single $$\boldsymbol{\cdot}$$, the shortest possible codeword, similarly $$\textrm{T}$$ and $$\textrm{A}$$ are also given pretty short codewords which are $$-$$ and $$\boldsymbol{\cdot}-$$ respectively meanwhile $$\textrm{Q}$$ has $$3$$ dashes and a dot making it the longest letter in terms of $$\#$$blinks, suggesting that certain kind of frequency analysis was considered while designing this code.

Unlike, previous codes encoding this code is slightly (but not too much :) challenging. The following tables helps in decoding received codewords back to messages

<p><a href="https://paramrathour.github.io/website-assets/morse-code-decoding.png" class="popup img-link light shimmer" target="_blank"><img src="https://paramrathour.github.io/website-assets/morse-code-decoding.png" alt="Morse Code (decoding)" loading="lazy"></a>
<a href="https://paramrathour.github.io/website-assets/morse-code-decoding.png" class="popup img-link dark shimmer" target="_blank"><img src="https://paramrathour.github.io/website-assets/morse-code-decoding.png" alt="Morse Code (decoding)" loading="lazy" style="filter: invert(100%) brightness(80%);"></a>
<em>Morse Code Decoding for English letters</em></p>

Let's try to decode, I have added appropriate [punctuation](#punctuation) of length $$1$$ dot, $$1$$ dash and $$2$$ dashes to distinguish between symbols, letters, and words respectively
<p>$$\boldsymbol{\cdot}\boldsymbol{\cdot}\,\,\,\,\,\,\boldsymbol{\cdot}-\boldsymbol{\cdot}\boldsymbol{\cdot}\,\,\,-\,-\,-\,\,\,\boldsymbol{\cdot}\boldsymbol{\cdot}\,\boldsymbol{\cdot}-\,\,\,\boldsymbol{\cdot}\,\,\,\,\,\,-\boldsymbol{\cdot}-\boldsymbol{\cdot}\,\,\,-\,-\,-\,\,\,-\boldsymbol{\cdot}\,\boldsymbol{\cdot}\,\,\,\boldsymbol{\cdot}\,\boldsymbol{\cdot}\,\,\,-\boldsymbol{\cdot}\,\,\,-\,-\boldsymbol{\cdot}\,\,\,\,\,\,-\,\,\,\boldsymbol{\cdot}\boldsymbol{\cdot}\,\boldsymbol{\cdot}\,\boldsymbol{\cdot}\,\,\,\boldsymbol{\cdot}\,\,\,-\,-\,-\,\,\,\boldsymbol{\cdot}-\boldsymbol{\cdot}\,\,\,-\boldsymbol{\cdot}-\,-$$</p>

Firstly, we have $\boldsymbol{\cdot}\,\boldsymbol{\cdot}$, which stands for $$\textrm{I}$$, then a punctuation for separating word, then $\boldsymbol{\cdot}-\boldsymbol{\cdot}\,\boldsymbol{\cdot}$, which is $$\textrm{L}$$, in this way you will figure out that this message is $$\textrm{I LOVE CODING THEORY}$$ and we have now shortened it to $$91$$ blinks, another $$33\%$$ reduction!
#### Issues with Morse Code

## Codes for Storage

## Codes for Error Detection and Correction