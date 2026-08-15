---
title: "Coding Theory: A Playful Introduction #SoME5"
description: "Let's cut through the noise, one bit at a time"
categories: [Math]
tags: [math, computer-science, sos, some]
date: 2026-05-17 16:20 +0530
math: true
---
> This post is designed for people with absolutely no idea about coding theory. Refer to
the [introduction](#introduction) in case you want to skip the basic stuff.\
Switch to light-mode and a bigger display for better experience.
{: .prompt-tip}

### A Problem
Imagine you are smol child in 1900s, you want to talk with your best friend at late night who is also your opposite neighbour. You don't want to disturb others (or perhaps wanna talk in secret), so you try speaking softly but the distance is too long to reach them, thankfully you both can see each other from your bedroom windows. The problem is how will you two communicate? Each of you has a flashlight 🔦 that you can use. Think about it![^code]

## Codes for Communication
### Attempt 1 (Drawing)
Well of course, you turn ON your flashlight and start drawing letters, you create the shape of $$\textrm{I}$$ with one single vertical stroke of your flashlight and then your friend can see the line and understand it. then you start drawing $$\textrm{L}$$ with one vertical stroke and an horizontal stroke below it from where you ended and realise that it will look as <span style="display:inline-block; transform: scaleX(-1);">
  $\textrm{L}$
</span> to your friend, so you need to draw <span style="display:inline-block; transform: scaleX(-1);">
  $\textrm{L}$
</span> then your friend interprets it correctly as $$\textrm{L}$$. then you draw an oval $$\textrm{O}$$ but wonder what if its interpreted as $$\textrm{0}$$, then you send $$\textrm{V}$$ with two simple storkes, then when you send <span style="display:inline-block; transform: scaleX(-1);">
  $\textrm{E}$
</span> you soon realise a bigger problem, interpreting symbols with many strokes isn't easy afterall the old strokes dont stay in the air until you finish the letter. So you wanted to do something more _precise_.

### Attempt 2 (Blinking)
Till now, your flashlight was always ON, you realise you havent turned it OFF since you started and then it clicks, what if you tried blinking (turning your flashlight ON and then OFF). To keep it simple, you _assign_ $$\textrm{A}$$ as $$1$$ blink, $$\textrm{B}$$ as $$2$$ blinks, and so on $$\textrm{Z}$$ as $$26$$ blinks. This works! 
To send $$\textrm{I LOVE}$$, you first blink your flashlight $$9$$ times then wait for some time and blink it $$12, 15, 22$$ and $$5$$ times. Your friend counts the number of blinks ($$\#$$blinks) and computes the letter sent. Of course, you need to make sure there is sufficient pauses between blinks, otherwise $$\textrm{I L}$$ can be interpreted as $$\textrm{U}$$ with $$9+12=21$$ blinks. also, you will need different pauses between $$\textrm{I}$$ and $$\textrm{L}$$ and $$\textrm{L}$$ and $$\textrm{O}$$ as one separates words and one separates letters of same word. Now $$\textrm{I LOVE}$$ is $$9+12+15+22+5=63$$ blinks, and it gets the job done. We can do better, but first celebrate as you have just discovered Coding Theory.

### Introduction
What you developed was a _code_, i.e., a system for transferring _information_ (in this case among people). This code helped you communicate the _message_ (something to be sent) by converting it into an _encoded message_ (something that's actually sent). A message is made up of _symbols_ (letters in our case) and an encoded message is made up of _codewords_ ($$\#$$blinks in our case). When you were converting a letter into $$\#$$blinks, you were _encoding_ and your friend was _decoding_ when they were converting $$\#$$blinks back into the letter. _Coding Theory_ is the study of such codes.
> This shouldn't be confused with the popular term with the same name 'coding' which means writing a computer program i.e., instructions for a computer.
{: .prompt-warning}

Now, let's get back to the problem.
### Attempt 3 (Frequency Analysis)
This discovery is great and as a result you want to send $$\textrm{I LOVE CODING THEORY}$$ next, well guess what, it turns out to be $$206$$ blinks, too long :(

But then, here you find your first breakthrough, you realise there is no need to map $$\textrm{A$-$Z}$$ to $$\textrm{1$-$26}$$ sequentially. From your futuristic experience of Scrabble, you know that letter $$\textrm{E}$$ comes up the most in english langauge, so why not assign it $$1$$ blink instead of $$5$$. and we can go ahead and assign second most frequent letter of the alphabet $$\textrm{T}$$ as $$2$$ blinks, to the third most frequent $$\textrm{A}$$ as $$3$$ blinks, and so on until the least frequent $$\textrm{Q}$$ and $$\textrm{Z}$$ as $$25$$ and $$26$$ blinks respectively, this ensures that we use fewer blinks for popular letters and hence can send our message faster.

Below table, gives an idea of frequency of each letter. Convince yourself that for any two pair of letters, it is better to represent the more frequent letter with lesser $$\#$$blinks to minimise the _expected_ total number of blinks.

![English letter frequency (alphabetic)](/frequency-analysis-letters-english-light.svg){: .light}
![English letter frequency (alphabetic)](/frequency-analysis-letters-english-dark.svg){: .dark}
_Frequency Analysis ($\%$) of English letters ([Image](https://commons.wikimedia.org/wiki/File:English_letter_frequency_(alphabetic).svg) by [Nandhp](https://commons.wikimedia.org/wiki/User:Nandhp) Public domain, via Wikimedia Commons)_

Using this, $$\textrm{I LOVE CODING THEORY}$$ is shortened to $$138$$ blinks, a whopping $$33\%$$ reduction!
### Punctuation
Before optimising our code further, let's discuss the important topic of punctuation. When we are sending our blinks, there are actually three levels of _pauses_ that we need to take between blinks for accurate decoding, these are
- pauses between blinks of same letter
- pauses between blinks of different letters
- pauses between blinks of different words

The technical term for these pauses is punctuation and it has been an important part of our codes till now.
### Attempt 4 (Morse Code)
Let's try to formalise our previous system. Instead of writing blinks over and over again, we can use codewords to represent our encoded message, so the letter $$\textrm{A}$$ means $$\bullet$$, $$\textrm{B}$$ means $$\bullet\bullet$$, $$\textrm{C}$$ means $$\bullet\bullet\bullet$$, and so on. This is essentially Base $$1$$ system of counting. Where, we literally have same number of $$\bullet$$'s (the length of the codeword) as number of blinks, akin to how ancient people used number of sticks to count their number of sheeps. 

> Notice that in this way, both our message and the corresponding encoded message can be represented by different sets of symbols, for our message the symbols are the alphabets whereas for the encoded message, the symbols are the dots, each specific collection of such dots form a codeword.

Here, we were using only one symbol $$\bullet$$, but what if we use two symbols instead? That's Base $$2!$$ With two symbols (say $$\bullet$$ and $$-$$ (called _bits_)) the possibilities explode, initially we had one codeword for every length, now there are $$2^n$$ codewords with length $$n$$, for eg, for length $$2$$, possible codewords are $$\bullet\bullet$$, $$\bullet-$$, $$-\bullet$$ and $$--$$. As, we now have many more codewords of short length, this will again shorten the _average_ length of the codewords and in turn, hopefully reduce $$\#$$blinks. But, what does the symbols $$\bullet$$ and $$-$$ represent here? Well, in Morse Code, people denote $$\bullet$$ by a short blink (dot) and $$-$$ by long blink (dash), in particular, a blink in a dash is __three times as long as__ a dot. Here, every letter of the alphabet can be written as a codeword comprised of dots and dashes as shown in below table

| Letter         | Symbol                           | Letter         | Symbol
| :--            | :--                              | :--            | :--
| $$\textrm{A}$$ | $$\bullet -                   $$ | $$\textrm{N}$$ | $$-\bullet $$               |
| $$\textrm{B}$$ | $$-\bullet\bullet\bullet      $$ | $$\textrm{O}$$ | $$--- $$                    |
| $$\textrm{C}$$ | $$-\bullet-\bullet            $$ | $$\textrm{P}$$ | $$\bullet--\bullet $$       |
| $$\textrm{D}$$ | $$-\bullet\bullet             $$ | $$\textrm{Q}$$ | $$--\bullet- $$             |
| $$\textrm{E}$$ | $$\bullet                     $$ | $$\textrm{R}$$ | $$\bullet-\bullet $$        |
| $$\textrm{F}$$ | $$\bullet\bullet-\bullet      $$ | $$\textrm{S}$$ | $$\bullet\bullet\bullet $$  |
| $$\textrm{G}$$ | $$--\bullet                   $$ | $$\textrm{T}$$ | $$- $$                      |
| $$\textrm{H}$$ | $$\bullet\bullet\bullet\bullet$$ | $$\textrm{U}$$ | $$\bullet\bullet- $$        |
| $$\textrm{I}$$ | $$\bullet\bullet              $$ | $$\textrm{V}$$ | $$\bullet\bullet\bullet- $$ |
| $$\textrm{J}$$ | $$\bullet---                  $$ | $$\textrm{W}$$ | $$\bullet-- $$              |
| $$\textrm{K}$$ | $$-\bullet-                   $$ | $$\textrm{X}$$ | $$-\bullet\bullet- $$       |
| $$\textrm{L}$$ | $$\bullet-\bullet\bullet      $$ | $$\textrm{Y}$$ | $$-\bullet-- $$             |
| $$\textrm{M}$$ | $$--      $$                     | $$\textrm{Z}$$ | $$--\bullet\bullet$$        |

Notice again that $$\textrm{E}$$ is just a single $$\bullet$$, the shortest possible codeword, similarly $$\textrm{T}$$ and $$\textrm{A}$$ are also given pretty short codewords which are $$-$$ and $$\bullet-$$ respectively meanwhile $$\textrm{Q}$$ has $$3$$ dashes and a dot making it the longest letter in terms of $$\#$$blinks, suggesting that certain kind of frequency analysis was considered while designing this code.

> We have a total of $2+2^2+2^3+2^4=30$ four-letter Morse Code combinations, but only 26 English alphabets. This leaves room for few accented characters like Ä, Ö, Ü and Ş to get shorter codeword compared to other accents.
{: .prompt-info}

Unlike, previous codes decoding this code is slightly (but not too much :) challenging. The following tree helps in decoding received codewords back to messages, it is essentially the previous table but converted into a tree. once we receive a codeword, we start from the _root_ of the tree at the extreme left and go to above branch for each dot and below branch for each dash; the letter we settle at after the codeword is done is the corresponding symbol of message.

![Morse Code Decoding for English letters](/morse-code-decoding-light.svg){: .light}
![Morse Code Decoding for English letters](/morse-code-decoding-dark.svg){: .dark}
_Morse Code Decoding for English letters_

Let's try to decode the text below, I have added appropriate [punctuation](#punctuation) of length $$1$$ dot, $$1$$ dash and $$2$$ dashes to distinguish between symbols, letters, and words respectively

<div style="overflow-x: auto; overflow-y: hidden;">
<p>$$\bullet\bullet\,\,\,\,\,\,\bullet-\bullet\bullet\,\,\,-\,-\,-\,\,\,\bullet\bullet\,\bullet-\,\,\,\bullet\,\,\,\,\,\,-\bullet-\bullet\,\,\,-\,-\,-\,\,\,-\bullet\,\bullet\,\,\,\bullet\,\bullet\,\,\,-\bullet\,\,\,-\,-\bullet\,\,\,\,\,\,-\,\,\,\bullet\bullet\,\bullet\,\bullet\,\,\,\bullet\,\,\,-\,-\,-\,\,\,\bullet-\bullet\,\,\,-\bullet-\,-$$</p>
</div>

Firstly, we have $\bullet\,\bullet$, which stands for $$\textrm{I}$$, then a punctuation for separating word, then $\bullet-\bullet\,\bullet$, which is $$\textrm{L}$$, in this way you will figure out that this message is $$\textrm{I LOVE CODING THEORY}$$ and we have now shortened it to $$91$$ blinks, another $$33\%$$ reduction!
#### Issues with Morse Code
While, we saw the huge importance of punctuation in our system, it also comes with some caveats.

Punctuation adds delay into our communication, adding to the time spent in spending a message when we do nothing, it would be much better if we could just flash dots and dashes consecutively. This delay is essentially acting as a third symbol (like `<space>` ) for our codewords. And so, Morse code can't be used for storing into today's memories as they strictly support only two symbols (which we denote by $$0$$ and $$1$$).

So can we just remove this delay, will our scheme still work? 

![Morse Code Decoding Overlap](/morse-tree-path-1-highlight-light.svg){: .light}
![Morse Code Decoding Overlap](/morse-tree-path-1-highlight-dark.svg){: .dark}
_Morse Code Decoding Overlap for Letters_

Look at the codewords of $$\textrm{E}$$, $$\textrm{A}$$, $$\textrm{R}$$, they are $$\bullet$$, $$\bullet-$$, $$\bullet-\bullet$$, notice something? Each codeword is a prefix of the following, this means if we receive $$\bullet-\bullet$$, we won't know whether it means $$\textrm{R}$$ or if it is $$\textrm{EN}$$ or if it is $$\textrm{AE}$$, if there was no punctuation. This existence of having prefixes of codewords as some another codeword makes unique decoding impossible.

#### Potential Solutions
There are two solutions to remove punctuation, let's look at each of them
##### Attempt 5 (Fixed-Length Coding)
First is by using a fixed length encoding scheme like ASCII (American Standard Code for Information Interchange), where all letters from $$\textrm{A}$$ to $$\textrm{Z}$$ are of $$8$$ bits (also called a _byte_) as shown in below table

| Letter         | Symbol       | Letter         | Symbol
| :--            | :--          | :--            | :--
| $$\textrm{A}$$ | $$01000001$$ | $$\textrm{N}$$ | $$01001110$$ |
| $$\textrm{B}$$ | $$01000010$$ | $$\textrm{O}$$ | $$01001111$$ |
| $$\textrm{C}$$ | $$01000011$$ | $$\textrm{P}$$ | $$01010000$$ |
| $$\textrm{D}$$ | $$01000100$$ | $$\textrm{Q}$$ | $$01010001$$ |
| $$\textrm{E}$$ | $$01000101$$ | $$\textrm{R}$$ | $$01010010$$ |
| $$\textrm{F}$$ | $$01000110$$ | $$\textrm{S}$$ | $$01010011$$ |
| $$\textrm{G}$$ | $$01000111$$ | $$\textrm{T}$$ | $$01010100$$ |
| $$\textrm{H}$$ | $$01001000$$ | $$\textrm{U}$$ | $$01010101$$ |
| $$\textrm{I}$$ | $$01001001$$ | $$\textrm{V}$$ | $$01010110$$ |
| $$\textrm{J}$$ | $$01001010$$ | $$\textrm{W}$$ | $$01010111$$ |
| $$\textrm{K}$$ | $$01001011$$ | $$\textrm{X}$$ | $$01011000$$ |
| $$\textrm{L}$$ | $$01001100$$ | $$\textrm{Y}$$ | $$01011001$$ |
| $$\textrm{M}$$ | $$01001101$$ | $$\textrm{Z}$$ | $$01011010$$ |
| `<space>`      | $$00100000$$ |

Even a space character has a codeword in ASCII $$(00100000)$$. So, a message like $$\textrm{I LOVE CODING THEORY}$$ which has a total of $$20$$ characters (including spaces), gets mapped to exactly $$20\times8=160$$ symbols. That's a lot of symbols yes, but we will see later how this is still an improvement. Decoding the received message is also pretty simple, divide it up into chunks of $$8$$ and individually decode each of the codeword to get back the message.

##### Prefix-Free Coding
![Morse Code Decoding Overlap](/morse-tree-path-2-highlight-light.svg){: .light}
![Morse Code Decoding Overlap](/morse-tree-path-2-highlight-dark.svg){: .dark}
_Morse Code Decoding Overlap for Letters_

Second solution is to only have codewords that are _prefix-free_, means no codeword should be a prefix of any other codeword. How can we achieve this? Take a look again at the decoding tree, the prefix ambiguity comes if there is any _internal node_, like $$\textrm{E, A, R}$$ are in the middle of the path from the root node to the _terminal node_ $$\textrm{L}$$. So, if we assign codewords such that all letters are at the terminal of the tree (also called _leaves_) then they will be prefix-free. 

Everything that we have learnt till now, will be used to explore this next example.
## Codes for Storage
### Attempt 6 (Huffman Code)

> Spoiler alert, Huffman Code is the limit of communication, it's the optimal way of communicating, you can't do better than this.
{: .prompt-info}

The encoding table and the decoding tree are shown as below:

| Letter         | Symbol         | Letter         | Symbol
| :--            | :--            | :--            | :--
| $$\textrm{A}$$ | $$1100$$       | $$\textrm{N}$$ | $$1000$$       |
| $$\textrm{B}$$ | $$101000$$     | $$\textrm{O}$$ | $$1011$$       |
| $$\textrm{C}$$ | $$00001$$      | $$\textrm{P}$$ | $$101001$$     |
| $$\textrm{D}$$ | $$11011$$      | $$\textrm{Q}$$ | $$1111001001$$ |
| $$\textrm{E}$$ | $$011$$        | $$\textrm{R}$$ | $$0001$$       |
| $$\textrm{F}$$ | $$111101$$     | $$\textrm{S}$$ | $$0101$$       |
| $$\textrm{G}$$ | $$101011$$     | $$\textrm{T}$$ | $$1110$$       |
| $$\textrm{H}$$ | $$0100$$       | $$\textrm{U}$$ | $$00000$$      |
| $$\textrm{I}$$ | $$1001$$       | $$\textrm{V}$$ | $$1111000$$    |
| $$\textrm{J}$$ | $$1111001010$$ | $$\textrm{W}$$ | $$111110$$     |
| $$\textrm{K}$$ | $$11110011$$   | $$\textrm{X}$$ | $$1111001011$$ |
| $$\textrm{L}$$ | $$11010$$      | $$\textrm{Y}$$ | $$101010$$     |
| $$\textrm{M}$$ | $$111111$$     | $$\textrm{Z}$$ | $$1111001000$$ |
| `<space>`      | $$001$$        |

Let's try an example $$\textrm{I LOVE}$$ can be encoded as following from looking up the encoding table $$1001{\color{skyblue}{001}}11010{\color{skyblue}{1011}}1111000{\color{skyblue}{011}}$$, note the color difference is just for us to better separate the letters it isn't actually used in the scheme.

![Huffman Code Decoding for English letters](/huffman-code-decoding-light.svg){: .light}
![Huffman Code Decoding for English letters](/huffman-code-decoding-dark.svg){: .dark}
_Huffman Code Decoding for English letters (Tree generated using [Huffman Coding Calculator](https://www.dcode.fr/huffman-tree-compression) by [dCode](https://www.dcode.fr/))_

Notice, already that there are no symbols at internal nodes implying that this code is prefix-free. Now, to decode our previous message, all we need to is start from the root node, and go up or down the branches appropriately, and as soon as we reach a leaf, we stop, that's one letter decoded and then we go back to root node and repeat the process. And, it will work!

<div style="overflow-x: auto; overflow-y: hidden;">
$$1001001110101011111100001100100001101111011100110001010110011110010001110110001101010$$
</div>

$$\textrm{I LOVE CODING THEORY}$$ in its entirety requires $$85$$ symbols which are shown above in their full glory. Before, we compare all our schemes, let's look at how a Huffman Tree is generated.


#### Huffman Tree Generation

Intuition
: Go back to the encoding table and, you will see that the codewords for $$\textrm{E}$$ (and `<space>`) have the shortest length and letters like $$\textrm{Q}$$, $$\textrm{Z}$$ are the longest, in fact more than thrice in length compared to the shortest codewords. This hints to our good old frequency analysis. In that analysis, we simply sorted all the frequencies and assigned a Base $1$ codeword based on rankings, which were linear. But, now we are working in Base $2$, so we get one more dimension to work with, and the number of combinations explode (like how we got $30$ codewords with only $4$ symbols in Morse). This significantly reduces the maximum possible length compared to our Base $$1$$ analysis.\
The second (more important) principle on which Huffman based his algorithm was also similar to our previous discussions. Just how less frequent symbols, got more $$\#$$blinks, even in Huffman Tree, less frequent symbols, get codewords of longer length, which ultimately will mean more $$\#$$blinks if used for communication. And so, this tree generation algorithm, always works to find least frequent symbols first to put those at more depth in tree.

![Huffman Code Generation](/huffman-code-generation-light.svg){: .light width="600"}
![Huffman Code Generation](/huffman-code-generation-dark.svg){: .dark width="600"}
_Huffman Code Generation for a sentence with six characters ([Image](https://en.wikipedia.org/wiki/File:Huffman_coding_visualisation.svg) by [Cmglee](https://commons.wikimedia.org/wiki/User:Cmglee) licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/))_

Now, the tree generation process, can be done for any message that you want to send. There are $$3$$ simple steps
- (initial step) sort the characters by frequency and put them in a list
- (repetitive step) merge the least frequent characters into a smol tree (partial tree) and reinsert this tree into the sorted list with the frequency equal to sum of frequency of characters that make up this tree
- keep doing the repetitive step until we use all the characters and are left with just one tree, the final tree

Ideally, the generated tree depends on sentence to be shared, and so while communicating every message, its generated tree should also be shared, as it will be needed for decoding. But for the purposes of my example, I constructed a general tree which can be used for all messages. This Huffman tree generation uses each letter with their frequency according to the discussed frequency analysis table. You can think of this as using a giant book as the "sentence" in the above tree creation process, since the frequencies of characters in a giant book will roughly match with frequency analysis table. So, we don't need to share this tree, as long as we agree on the frequencies, our tree will be the same, right? Well, there is a little technicality. Let's look at 4 in the tree generation image. What if $$\textrm{A}$$ also had frequency of $$10$$, then we will have a three-way tie between the `<space>`, $$\textrm{A}$$ and $$\textrm{D}$$. We can pick any two of them and continue from there. But each such combination will lead to a different tree. So, if we want to generate the same trees every time, we also need to follow same _convention_ to break these ties, one possible example could be always picking up the "earliest" letter pair and giving the highest priority to `<space>` if it is present. So, as long as we agree on the frequencies and our conventions, our tree will be the same, and we don't need to send it everything.
{: .prompt-info}

## Comparison of Schemes

How to even compare all these schemes? To start simply, let's us look at all encodings together. The length roughly gives us some idea on how good a scheme is. I have replaced the dots and dashes of Morse with $$0$$ and $$1$$ respectively for easier comparison.

| Attempt | Scheme Name                 | Encoding of $$\textrm{I LOVE CODING THEORY}$$
| :--     | :--                         | :--
| 2       | Blinking a.k.a. Base $$1$$      | $111111111\,\,\,111111111111\,111111111111111\,1111111111111111111111\,11111\,\,\,111\,111111111111111\,1111\,111111111\,11111111111111\,1111111\,\,\,11111111111111111111\,11111111\,11111\,111111111111111\,111111111111111111\,1111111111111111111111111$
| 3       | Base $$1$$ + Frequency Analysis | $11111\,\,\,11111111111\,1111\,111111111111111111111\,1\,\,\,1\,11111111111\,1111\,1111111111\,11111\,111111\,11111111111111111\,\,\,11\,11111111\,1\,1111\,111111111 111111111111111111$
| 4       | Morse Code                  | $0\,0\,\,\,\,\,\,0\,1\,0\,0\,\,\,1\,1\,1\,\,\,0\,0\,0\,1\,\,\,0\,\,\,\,\,\,1\,0\,1\,0\,\,\,1\,1\,1\,\,\,1\,0\,0\,\,\,0\,0\,\,\,1\,0\,\,\,1\,1\,0\,\,\,\,\,\,1\,\,\,0\,0\,0\,0\,\,\,0\,\,\,1\,1\,1\,\,\,0\,1\,0\,\,\,1\,0\,1\,1$
| 5       | ASCII                       | $0100100100100000010011000100111101010110010001010010000001000011010011110100010001001001010011100100011100100000010101000100100001000101010011110101001001011001$
| 6       | Huffman Code                | $1001001110101011111100001100100001101111011100110001010110011110010001110110001101010$

While, Morse looks the shortest, remember that its dash is three times longer than a dot. Whereas, the $0$'s and $1$'s of ASCII and Huffman can be sent in the same time of one blink. How? That's the genius of [Line Coding](#appendix-line-coding), which is added as an appendix for interested folks. Then to compare all these schemes, we can easily calculate the time taken to transmit the message $\textrm{I LOVE CODING THEORY}$ for all the schemes. Let's formalise this, restricting each blink to mean ON for $$½$$ second.


### Attempt 2 (Base $$1$$)
Here, our encoded message consists of blinks and three levels of _pauses_ as discussed earlier. The time taken by each part is
- Blink: $$½$$ second
- Pause
  - Within Letters: $$½$$ second
  - Between Letters: $$1 ½$$ second
  - Between Words: $$3$$ second

We can calculate the total time taken, by calculating time taken by each part independently and summing them together like below

<div style="overflow-x: auto; overflow-y: hidden;">
$$
\begin{align}
t &= \text{time spent blinking }+\text{pause within letters }+\text{pause between letters }+\text{pause between words}
\end{align}
$$ 
</div>

So, the total time taken by our 2<sup>nd</sup> attempt $t_2$ for any sending any collection of words is given by 

<div style="overflow-x: auto; overflow-y: hidden;">
$$
\begin{align}
t_2 &= \underbrace{\text{#blinks}\cdot½}_{\text{time spent blinking}} + \underbrace{(\text{#blinks}-\text{#letters})\cdot½}_{\text{pause within letters}} + \underbrace{(\text{#letters}-\text{#words})\cdot1½}_{\text{pause between letters}} + \underbrace{(\text{#words}-1)\cdot3}_{\text{pause between words}}
\end{align}
$$ 
</div>

Try to pause and understand how this formula works maybe using our example, I have already split it into parts so that it is easy to derive. A key hint is to first try to calculate the time for a single letter, then a single word and then finally a collection of word, if you are able to correctly solve for single letter, you have already completed halt the job, the last half is just about recognising the pattern and using it for next calculations.\
Now, getting the value for the message $\textrm{I LOVE CODING THEORY}$ is a matter of trivial substitution into this formula.

<div style="overflow-x: auto; overflow-y: hidden;">
$$
\begin{align*}
t_2 &= \underbrace{\text{206}\cdot½}_{\text{time spent blinking}} + \underbrace{(\text{206}-\text{17})\cdot½}_{\text{pause within letters}} + \underbrace{(\text{17}-\text{4})\cdot1½}_{\text{pause between letters}} + \underbrace{(\text{4}-1)\cdot3}_{\text{pause between words}}\\
t_2 &=  226\, \text{seconds} 
\end{align*}
$$
</div>

### Attempt 3 (Base $$1$$ + Frequency Analysis)
Notice, the structure of our encoded message in this and previous attempt is the same (Base $$1$$). The only difference between this and previous attempt is that now, $$\#$$blinks for every letter is according to their frequency, so the total time spent blinking ($$\#$$blinks) may change, but rest of our analysis, will still work, as a result, the same formula works!

<div style="overflow-x: auto; overflow-y: hidden;">
$$
\begin{align}
t_3 &= \underbrace{\text{#blinks}\cdot½}_{\text{time spent blinking}} + \underbrace{(\text{#blinks}-\text{#letters})\cdot½}_{\text{pause within letters}} + \underbrace{(\text{#letters}-\text{#words})\cdot1½}_{\text{pause between letters}} + \underbrace{(\text{#words}-1)\cdot3}_{\text{pause between words}}
\end{align}
$$ 
</div>

Now, let's try substituting values into it

<div style="overflow-x: auto; overflow-y: hidden;">
$$
\begin{align*}
t_3 &= \underbrace{\text{138}\cdot½}_{\text{time spent blinking}} + \underbrace{(\text{138}-\text{17})\cdot½}_{\text{pause within letters}} + \underbrace{(\text{17}-\text{4})\cdot1½}_{\text{pause between letters}} + \underbrace{(\text{4}-1)\cdot3}_{\text{pause between words}}\\
t_3 &=  158\, \text{seconds}
\end{align*}
$$
</div>

### Attempt 4 (Morse Code)
Even, this analysis is similar, let's breakdown a message encoded using Morse and the time taken by each part 
- Dot: $$½$$ second (same as Blink)
- Dash: $$1½$$ second (3 Dots)
- Pause
  - Within Letters: $$½$$ second (Dot)
  - Between Letters: $$1 ½$$ second (Dash)
  - Between Words: $$3$$ second (2 Dash)

Now, can you write down the formula just by using previous formulae? Think about it!
All we did which thinking about this Base $$2$$ method was adding another symbol (dash) to our Base $$1$$'s blink (dot). So, only $$\#$$blinks part in the formula needs updation and there we have it

<div style="overflow-x: auto; overflow-y: hidden;">
$$
\begin{align}
t_4 &= \underbrace{\text{#dots}\cdot½+\text{#dashes}\cdot1½}_{\text{time spent blinking}} + \underbrace{((\text{#dots}+\text{#dashes})-\text{#letters})\cdot½}_{\text{pause within letters}} + \underbrace{(\text{#letters}-\text{#words})\cdot1½}_{\text{pause between letters}} + \underbrace{(\text{#words}-1)\cdot3}_{\text{pause between words}}
\end{align}
$$ 
</div>

Notice, the 'time spent blinking' and 'pause within letters', have different multiplication factors to $$\#$$dashes, this is because a dash blinks for longer time than a dot, but they both count as only one blink, one is short blink and another is long blink. So, the two $$\#$$blinks terms in our previous formula were used for different purposes, which is why I had kept the formula as it is instead of simplifying it further, which can later cause confusion, if we tried generalising that formula.
So, the time taken is...

<div style="overflow-x: auto; overflow-y: hidden;">
$$
\begin{align*}
t_4 &= \underbrace{\text{25}\cdot½+\text{22}\cdot1½}_{\text{time spent blinking}} + \underbrace{((\text{25}+\text{22})-\text{17})\cdot½}_{\text{pause within letters}} + \underbrace{(\text{17}-\text{4})\cdot1½}_{\text{pause between letters}} + \underbrace{(\text{4}-1)\cdot3}_{\text{pause between words}}\\
t_4 &=  89\, \text{seconds}
\end{align*}
$$
</div>

### Attempt 5 (ASCII)
Now, for our remaining attempts, remember that we don't have any pauses, so we can take $0$ as not blinking, and $1$ as blinking. This will work for us, though there are better ways to do this and we will discuss them later. So, for both ASCII and Huffman, we can simply write the time taken as

$$
\begin{align}{\label{eq:nopauses}}
t_{5 || 6} &= \text{#0}'s\cdot½ + \text{#1}'s\cdot½
\end{align}
$$ 

Now for ASCII, this means

<div style="overflow-x: auto; overflow-y: hidden;">
$$
\begin{equation}
\begin{aligned}[b]
t_5 &= (\text{#0's} + \text{#1's})\cdot½\\
&= 8\cdot\text{#characters}\cdot½\\
&= 8\cdot(\text{#letters} + \text{#spaces})\cdot½\\
&= 8\cdot(\text{#letters} + (\text{#words} - 1))\cdot½\\
t_5 &= 4\cdot(\text{#letters} + \text{#words} - 1)\\
\end{aligned}
\end{equation}
$$ 
</div>

Substituting numbers, we get

$$
\begin{align*}
t_5 &= 4\cdot(17 + 4- 1)\\
t_5 &=  80\, \text{seconds}
\end{align*}
$$

### Attempt 6 (Huffman Code)
Here, we use equation $\ref{eq:nopauses}$ directly, since every character can have variable number of $$\#0$$'s and $$\#1$$'s, so it's better to count all of them and calculate the answer

$$
\begin{align*}
t_6 &= (\underbrace{40}_{\text{#0's}} + \underbrace{45}_{\text{#1's}} ) \cdot½\\
t_6 &=  42.5\, \text{seconds}
\end{align*}
$$

So, the final numbers turns out to be as shown below.

| Attempt | | Scheme Name                     | Time Taken (in seconds) to transmit $\textrm{I LOVE CODING THEORY}$
| :--     | | :--                             | :--
| 2       | | Base $$1$$                      | $226$
| 3       | | Base $$1$$ + Frequency Analysis | $158$
| 4       | | Morse Code                      | $89$
| 5       | | ASCII                           | $80$
| 6       | | Huffman Code                    | $42.5$

$42.5$ seconds is just a fifth of the time to transmit 'our message' compared to our initial naive attempt $$\#$$2 of blinking a flashlight. 


### The Limits of Compression
You might question the authenticity of our analysis, what happens if the message changes? Is Huffman still the best? and by how much?

You might wonder if we can do better than Huffman Code, if it is possible to keep reducing the time taken forever.

These are all valid questions, firstly I encourage everyone to work out the timings for other sentences, and secondly, it is also possible to do a probabilistic analysis (using our good old frequency tables) and find out the _average_ performance of each schemes. I leave this exercise to you :)

Now, coming to the big results __Huffman Code is the limit!__. Yup, you can't really do better than it. Do check out this awesome video[^reducible], which dives into Information Theory. Essentially, the idea is to mathematically calculate the _information_ content within our message, and prove that Huffman Code either matches it or comes as close as possible for a code.

> Another doubt could be, why not use Base $$3$$ or $$4$$ or higher? after all, we just witnessed these wild improvements from Base $$1$$ to $$2$$. Let's go back to our setup, what Base $$2$$ really meant was their were $2$ states that our flashlight could be: either OFF or ON. But modern flashlight comes with brightness levels, as long as you and your friend are able to distinguish these brightness levels, go ahead and experiment! Things will definitely be easier, after all in Base $$27$$ (alphabets+space), our message $$\textrm{I LOVE CODING THEORY}$$ is just $20$ characters, so it will take just $10$ seconds to transfer it using a flashlight with at least $26$ different brightness levels (and an OFF state). So, the time taken to send the message definitely reduces with more _symbols_. You can even try creating a $n$-ary Huffman Tree with $n$ children at each node compared to the $2$ children for Base $$2$$ case, it will still work with some catch. So, how is our original Huffman Code _optimal_? It is optimal not in terms of time taken or length but in terms of _compression_. And compression is about _storage_. It's about storing a particular piece of information in a _digital_ computer using minimum amount of resources possible. Since, our computers use bits, which are either $0$ or $1$, a $2$-ary Huffman Tree utilises the computer's resources optimally with minimum wastage. Even if we use say, $4$ symbols, and compute our optimal codewords using $4$-ary Huffman Tree, ultimately each of these $4$ symbols will need to be converted to a binary number needing $2$ symbols ($00$, $01$, $10$, $11$) so that our computers can process it. But, after everything is converted to $2$ symbols, the resultant codewords of a $2$-ary Huffman Tree are optimal, and its codewords are not necessarily the same as the codewords generated from the $4$-ary Huffman Tree, which will be all even length in base $2$.\
\
_Future computing developments may change our the foundational unit of computation from something other than bits, but we don't need to look into the future, instead look into the nature, look at the DNA, the instruction manual of our body, which stores our entire genome, it is built from $$4$$ chemical bases <strong>Adenine (A), Thymine (T), Cytosine (C) and Guanine (G)</strong>. Isn't this fascinating?_
{: .prompt-info}

## Conclusion?
And with that, we have reached what I would call as a significant point of our journey. Congrats! You made it till here. You have my thanks for reading this blog and I hope you will keep enjoying it. Before we start again, now is the best time to sit back, and think of what we have accomplished. Recollect our progression, how we started from _Blinking_, _Frequency Analysis_, _Morse-code_, _ASCII_ and made our way up till _Huffman_ and think, are we done here? After all, we even saw the optimal Huffman Code, so what's left? Come back once you have thought about this again.

### Issues with Huffman Code
#### Fixed Alphabet
While, my home grown Huffman Code tree will work for our English alphabet and the `<space>` characters, what if one day we decided to add more details into our messages by using punctuation marks‽ or you try to practice new language that you have recently started learning, and send its characters (good luck going through 100,000 Kanji characters :), can you talk about your math homework without numbers or math symbols ∅

Currently, all our system is fixed, we think about frequencies, make a tree and call it a day. So, how can we make our system dynamic, where we can continuously keep adding stuff. The answer is 🥁... <strong>Unicode</strong>! One of the most incredible man-made inventions, which is what the entire modern web is built around. All the text on this and other website (including the emojis and math-equations) is represented by it. Unicode is THE standard way of exchanging text within computers. You might have come directly across the term UTF-8, when trying to save `.txt` files or indirectly wͮͮ̒h̴̠͉̿͆ͧe̵̍̍̿ñ̜͊ y͉̳̅o͔̙̫u̦̣͗̇̂ r̮̱̅ͥe̵͉͆c̴ͤe̴͍͓i͒̇v̜̦̌e̷͕͎̩̔ͭͧd̴  an English message that seemed corrupted[^glitch]. But if you are wondering wtf is UTF-8, then do check the Tom Scott video[^utf8] on this.

Essentially, it is the culmination of things that we have learnt today.
- It is a variable length encoding scheme where the codeword is in $1$-$4$ chunks of a byte (i.e., $8$ bits), meaning the total length varies from $8$ to $16$/$24$/$32$ bits.
- All the $8$ bit codewords correspond to ASCII, the 'most popular' language on the internet.
- It is also a prefix-free code, as no codeword can be a prefix of another. This can be visually seen from the below diagram as the start of all the codewords of different length is different.

![UTF-8 Encoding in a Nutshell](/utf8-structure-light.svg){: .light}
![UTF-8 Encoding in a Nutshell](/utf8-structure-dark.svg){: .dark}
_UTF-8 Encoding in a Nutshell[^utf8codewords]_

I can go through a few examples, but I am intentionally keeping this section short, so that if you are curious you can check it out yourself.
#### Errors 
Would you believe me if I said missed a very important point in our analysis? This might start to feel annoying unless you thought it about during your break-time. What if while sending message, your friend makes an error? Say they themselves blinked while you were blinking your flashlight and hence misinterpreted a $1$ as $0$. Will this have any impact on your message.

Well, let's go through our codes again, and try to decode our original message but here the fourth bit has mistankely as $0$ instead of $1$.

<div style="overflow-x: auto; overflow-y: hidden;">
$$100100{\color{orangered}{0}}110101011111100001100100001101111011100110001010110011110010001110110001101010$$
</div>

![Huffman Code Decoding for English letters](/huffman-code-decoding-light.svg){: .light}
![Huffman Code Decoding for English letters](/huffman-code-decoding-dark.svg){: .dark}
_Huffman Code Decoding for English letters_

<div style="overflow-x: auto; overflow-y: hidden;">
$$\underbrace{1001}_{\textrm{I}}\underbrace{00{\color{orangered}{0}}1}_{\textrm{R}}\underbrace{101010}_{\textrm{Y}}\underbrace{111111}_{\textrm{M}}\underbrace{00001}_{\textrm{C}}\underbrace{1001}_{\textrm{I}}\underbrace{00001101111011100110001010110011110010001110110001101010}_{\textrm{CODING THEORY}}$$
</div>

Decoding it using the Huffman tree, we get the message as $\text{I}{\color{orangered}\text{RYMCI}}\text{CODING THEORY}$, and we lost out on $\textrm{LOVE}$ 😭. So, if even one bit was actually misinterpreted then it can corrupt future codewords and there is no way to recover them other than guessing. Will this big impact happen with ASCII and Morse too, what do you think? 

As ASCII is fixed-length, if just one bit was corrupted then it will only have an effect on the $8$ bits that contain it, so max one character will be different. So, if we had received

<div style="overflow-x: auto; overflow-y: hidden;">
$$010010{\color{orangered}{1}}100100000010011000100111101010110010001010010000001000011010011110100010001001001010011100100011100100000010101000100100001000101010011110101001001011001$$
</div>

then it gets decoded as ${\color{orangered}\text{K}}\text{ LOVE CODING THEORY}$.

And, for Morse

<div style="overflow-x: auto; overflow-y: hidden;">
$$0\,0\,\,\,\,\,\,0\,1\,0\,0\,\,\,{\color{orangered}{0}}\,1\,1\,\,\,0\,0\,0\,1\,\,\,0\,\,\,\,\,\,1\,0\,1\,0\,\,\,1\,1\,1\,\,\,1\,0\,0\,\,\,0\,0\,\,\,1\,0\,\,\,1\,1\,0\,\,\,\,\,\,1\,\,\,0\,0\,0\,0\,\,\,0\,\,\,1\,1\,1\,\,\,0\,1\,0\,\,\,1\,0\,1\,1$$
</div>

we get, ($\text{I L}{\color{orangered}\text{W}}\text{VE CODING THEORY}$), even though this is variable length like Huffman, it worked out thanks to its pauses. Of course, this is an artificial example of flipping the seventh bit for some reason, but the lesson is while we do get ultimate compression using Huffman Code, we lose out on its _error-correction_ capabilities. This makes intuitive sense too, as Huffman was able to compress well because it removed any sort of redundant information from it.

## Types of Coding
Till now, we studied about __Source Coding__, which was all about encoding and _data compression_, though in particular, we explored concepts in _lossless_ compression, that makes it possible to perfectly reconstruct our message from our encoded message. Another important branch of Coding Theory is __Channel Coding__ which goes deep into this analysis of possible errors (like _noise_) during communication and uses codes to add redundancy instead for _reliable communication_.

Think of another possibility, this time you want to communicate about your love (of coding theory of course) in _secret_, so that no one apart from your friend is able to understand the message. This is the problem of __Cryptographic Coding__, which is about _secure_ communication. With channel coding, ideally we want to be able to decode our encoded message in any case, even in presence of lot of noise, but in cryptography, we only want the intended receivers to be able to ~~decode~~ decrypt our ~~encoded message~~ ciphertext and to other observers our message should be nothing but _random_ noise, since if it had any patterns, those patterns can be used to get back the original message.

This leaves us with the last type, which will be discussed now!

## Appendix: Line Coding
Remember that I made this point that the $0$'s and $1$'s of ASCII and Huffman can be sent in the same time of one blink ($$½$$ second). __Line Coding__ helps to represent our _binary_ data of $0$'s and $1$'s into _physical data_. Generally, voltages (either HIGH or LOW) do this task, but in our example, we are using flashlights :)

> Feel free, to skip this section as it is more of a rambling than an explanation.
{: .prompt-tip}

So the way it is done, is pretty intuitive, we are past blinking now (or are we?). We just need to keep our flashlight ON if we want to send $1$ for $$½$$ second and then OFF for $0$. And, we are done with our full text in $42.5$ seconds.

But, let's dive a bit deeper, look at the first plot of below figure. Here, our message $\textrm{I LOVE}$ is encoded using Huffman Code. This simple scheme has a simple name: _On--off keying_ and a mouthful name: Non-Return-to-Zero Level (NRZ-L), which will (hopefully) make sense after looking at other schemes. 

![Line Coding Schemes](/line-coding-light.svg){: .light}
![Line Coding Schemes](/line-coding-dark.svg){: .dark}
_Line Coding Schemes (Timing Diagrams)_

Again, let's think about its issues (the diagram will help). Notice, how there are $6$ consecutive ones from bit $15$ to $20$ ($7$ to $10$ seconds). That means, our flashlight will be ON for $6\cdot½=3$ seconds. The longer the time, the difficult it becomes for humans to keep measuring it accurately, which makes it possible to misinterpret $6$ ones as $5$ or $7$ ones. The technical term for it is _clock synchronisation_, where we want both the sender and receiver to have the same perception of a $½$ second. So, it's preferable to have more _toggles_ (switches from $0$ to $1$ or vice versa) to minimise this error in perception.

Let's try to solve this. How about we toggle our flashlight every time we need to send a $1$? Then even if we have a string of $1$'s, our flashlight will keep toggling and thus we won't need to measure time for long, but wait, in this case, we can't toggle when we need to send $0$, otherwise, there will be no difference between the behaviour across bits, and subsequently, no distinguishability for the person observing our flashlight. So, when we need to send $0$, we do nothing, and don't change the flashlight's state. This is the Non-Return-to-Zero Inverted (NRZ-I) scheme. Sadly, as evident from the timing diagram; this scheme doesn't work as it won't toggle if the encoded message is continuously $0$ or alternating between $0$'s or $1$'s. But, this scheme does do something _interesting_, now we don't need to know whether flashlight ON is $0$ or $1$, since what matters is the _switching_ of flashlights, so even if the output is reverse of what we are sending now it will still work for all bits except first bit. This case is not possible for our flashlight communication, but it is easily possible in electrical wires where they can get twisted (like USBs) and affect the direction of voltage. To appreciate it, we can think of a flashlight which is always ON but supports two colours, don't you think now it will be difficult to remember, which colour is $0$ and which one is $1$? With NRZ-I, we don't need to.

> Just as a convention, we _start by keeping the flashlight ON_, this helps in determining the first bit for few schemes like NRZ-I.
{: .prompt-tip}

Both of the above schemes had large sections of constant behaviour, leading to synchronisation issues. So, what if we added toggles every time we send data? Say, if we are sending $1$, then we will turn the flashlight OFF for first half of time and turn it ON for next half (then the output will go from _low_ to _high_) and the opposite for sending $0$ (ON then OFF). Since, now, we will at zero for the half the time, these types of scheme are called Return-to-Zero coding.

This specific scheme is _Manchester_ coding scheme and the diagram speaks for itself. Now, a toggle is guaranteed to happen for every sent bit at the middle of encoded data (odd multiples of $0.25$ seconds). So, even if you just look at the Manchester data, the decoding is obvious if you look at any part with alternating bits, as they will have a one second window with no toggles inside them. Say if we are only looking at the output data, then we will observe no toggle from $6.75$ to $7.25$ seconds. Now, we need to look at the timing behaviour at $t=7.25$ seconds, and that gives you the toggle associated with going from low to high, so from $7$ to $7.5$ seconds, the output is $1$ and then once we find a bit, it is easy to follow it and get all other bits.

Okay, so what's with the last one? It is a mixture of NRZ-I and Manchester called _Differential Manchester_, taking the best of the both worlds, it has the toggles, and flipping the outputs won't affect the decoding either. Figuring out how this works, will be an engaging exercise :)

> For the RZ coding schemes, I have reduced minimum toggling time from $$½$$ to $$¼$$ seconds, so that all the plots line up, but for a fair comparison, I should have kept minimum time same, which would have meant, the RZ schemes ($85$ seconds) would take twice the time compared to NRZ schemes ($42.5$ seconds) and very close to Morse Code ($89$ seconds). Though, this doesn't really invalidate our comparison, as if we change to RZ schemes, we should use RZ for Morse and that will roughly double the time for it too.
{: .prompt-warning}

## Conclusion
And with that, we have reached the goal of the problem, you now know the most efficient scheme to communicate with your best friend (don't forget this was set-in 1900s :), and hopefully you learnt interesting things with this journey. 

Though there is a lot more to be said, especially for _Channel Coding_ and _Cryptographic Coding_, I hope with this problem I have ignited enough interest for you to start your own journey with Coding Theory. I have added few[^ecc] interesting[^qr] videos[^reedsolomon] about Error-Correcting Codes, feel free to check them out. And you can leave any questions for me in the comments section.

If you have read all of my ramble, I genuinely thank you. Apologies for the abysmal grammar and poor writing. I wasn't able to work on it as much as I wanted to. Still, I will get back and tidy this up (once the event finishes). And with that I finally take leave ✌️

## References
[^code]: This beautiful problem from the the book [Code: The Hidden Language of Computer Hardware and Software](https://www.codehiddenlanguage.com/) by [Charles Petzold](https://www.charlespetzold.com/) inspired me to build ideas on top of it and create this blog post with my own narrative.
[^reducible]: [Huffman Codes: An Information Theory Perspective]({{ site.url_prefixes.youtube.video }}/B3y0RsVCyrw) by [Reducible](https://www.youtube.com/@Reducible)
[^glitch]: Glitch text generated using [Glitch Text Generator](https://coddy.tech/tools/glitch-text-generator) -- [Coddy](https://coddy.tech/)
[^utf8]: [Character Encodings and UTF-8]({{ site.url_prefixes.youtube.video }}/MijmeoH9LT4) by [Computerphile](https://www.youtube.com/@Computerphile)
[^utf8codewords]: [UTF-8]({{ site.url_prefixes.wikipedia }}/UTF-8) by [Wikipedia](https://www.wikipedia.org/)
[^ecc]: [The Hidden Geometry of Error-Free Communication]({{ site.url_prefixes.youtube.video }}/Tmx-v4FiP6I) by [AnotherRoof](https://www.youtube.com/@AnotherRoof)
<!-- [^hamming]: [But what are Hamming codes? The origin of Error Correction]({{ site.url_prefixes.youtube.video }}/X8jsijhllIA) by [3Blue1Brown](https://www.youtube.com/@3blue1brown) -->
[^qr]: [I built a QR code with my bare hands to see how it works]({{ site.url_prefixes.youtube.video }}/w5ebcowAJD8) by [Veritasium](https://www.youtube.com/@veritasium)
[^reedsolomon]: [What Are Reed-Solomon Codes? How Computers Recover Lost Data]({{ site.url_prefixes.youtube.video }}/1pQJkt7-R4Q) by [vcubingx](https://www.youtube.com/@vcubingx)
