---
layout: post
title: LaTeX Tips
description: "Newbie's roadmap: getting started with resources to the ultimate setup!"
categories: [Programming, Tutorial]
tags: [latex, programming, tutorial, tips]
math: true
pin: true
date: 2023-12-17 08:21 +0530
---
## History
While working on his magnum opus, 'The Art of Computer Programming', Donald Knuth was disappointed with the quality of typesetting which led him to develop $$\TeX$$, a typesetting system intended for the creation of beautiful books that contain a lot of mathematics[^texbook]. With Leslie Lamport's modifications, $$\LaTeX$$ was born.

## Features
Unlike a <span data-bs-toggle="tooltip" data-bs-placement="top" title="What You See Is What You Get">WYSIWYG</span> software, here an individual writes code and the document is generated automatically. This allows users to focus on writing actual content while the software takes care of text formatting and document layout.

Here are some of its advantages
- Support for complex math expressions and enviroments
- Automatic numbering and generation of table of contents, citations and other lists 
- Active open-source community has developed packages[^ctan] for pretty much everything

You really don't need to know anything else about it, you will pick up things as you dive deeper. Now, let's begin.
## Getting Started

You can use [Overleaf](https://www.overleaf.com?r=8d4792b1&rm=d&rs=b) to start your $$\LaTeX$$ journey. The [Learn LaTeX in 30 minutes](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes) blog will explain you the basics. And that's it! You can now use overleaf to work on any document.

### Resources
- [LaTeX Course by Learner's Space, IIT Bombay](https://github.com/paramrathour/LaTeX) - A concise course that covers pretty much all the basics and gives you a flavour of advance stuff.
- [LaTeX Tutorial](https://latex-tutorial.com/tutorials) - Short and sweet tutorials covering various $$\TeX$$nical concepts. This is from where I learnt but the [Overleaf tutorials and guides](https://www.overleaf.com/learn) are also good.
- [$$\LaTeX$$ in 24 Hours](https://link.springer.com/book/10.1007/978-3-319-47831-9) - This book is an overkill, but this really shows off what $$\LaTeX$$ can do.
- [The $$\TeX$$book](https://ctan.org/pkg/texbook?lang=en) - The book by the creator himself is like an overkill on steroids, if that makes sense.
- [Comprehensive $$\TeX$$ Archive Network](https://ctan.org/) (CTAN) - The holy documentation, something everyone should read at some point in their life, right?
- [Awesome LaTeX](https://github.com/egeerardyn/awesome-LaTeX) - A list of list of awesome $$\LaTeX$$ things.

> Also, do check out this [tutorial](https://aryamanmaithani.github.io/latex/) by Aryaman Maithani, especially the "things to keep in mind" section to learn it the correct way. He's the guy who inspired me to delve into $$\LaTeX$$.
{: .prompt-tip}

These resources are handy, but if you ever get stuck, just Google it, and you'll get what you want.\
Trust me, the [$$\TeX$$ - $$\LaTeX$$ Stack Exchange](https://tex.stackexchange.com/) is a lifesaver for literally any $$\TeX$$nical doubt.

#### Online Tools
- [Detexify](https://detexify.kirelabs.org/classify.html) - Recognises hand-drawn symbols and it provides the corresponding $$\LaTeX$$ command and packages to import if any.

Just to make it clear, if coding something gets too complex, you can always turn to online GUI tools such as
- [Table Generator](https://www.tablesgenerator.com/) - Helpful for messy tables with merged cells and custom borders.
- [Finite State Machine Designer](https://madebyevan.com/fsm/)

and many more!

## Offline Setup
Once you get a good grasp with $$\LaTeX$$, go for an offline setup.

I use Sublime Text with `LaTeXTools`, `LaTeXYZ` and `LaTeX-cwl` packages to speed up writing program.
![sublime-text-latex-math-render](/sublime-text-latex-math-render.gif){: w="100%"}
_Gaussian function of a normally distributed random variable with expected value $$=\mu$$ and standard deviation $$=\sigma$$_
### Benefits
- Keyboard Shortcuts
- Autocompletions and Automatching
- Equation and Image Preview
- Forward Search and Inverse Search
- Spell Checking
- Custom Builders and many more

For this, you need to follow the steps mentioned in this blog, [Set up Sublime Text as Your Ultimate LaTeX Editor](https://jdhao.github.io/2018/03/10/sublime-text-latextools-setup/).
I have summarized the important points below.

### Installation
- LaTeX - Either [TeX Live](https://www.tug.org/texlive/acquire.html) or [MikTeX](https://miktex.org/) works.
- [Sublime Text](https://www.sublimetext.com/download) - A light-weight but powerful text editor with support for many programming languages.
	- [Package Control](https://packagecontrol.io/installation)
		- [`LaTeXTools`](https://packagecontrol.io/packages/LaTeXTools)
		- [`LaTeXYZ`](https://packagecontrol.io/packages/LaTeXYZ)
		- [`LaTeX-cwl`](https://packagecontrol.io/packages/LaTeX-cwl)
- [Sumatra PDF Viewer](https://www.sumatrapdfreader.org/download-free-pdf-viewer) - A superfast and light-weight `pdf` viewer which also supports `epub`, `djvu`, `mobi`, `cbz` and many other document formats with customizable [keyboard shortcuts](https://www.sumatrapdfreader.org/docs/SumatraPDF-documentation).


### Configuration Steps
- [Configure Inverse Search](https://jdhao.github.io/2018/03/10/sublime-text-latextools-setup/#configure-inverse-search-for-pdf-files)
- Check out keyboard shortcuts for [`LaTeXTools`](https://latextools.readthedocs.io/en/latest/keybindings/) and [`LaTeXYZ`](https://packagecontrol.io/packages/LaTeXYZ)
- Fix [new window open](https://github.com/SublimeText/LaTeXTools/issues/1530#issuecomment-880503345) and [autocomplete](https://github.com/SublimeText/LaTeXTools/issues/1506#issuecomment-775060589) problem if it occurs.
- Optionally, install more [recommended packages](https://latextools.readthedocs.io/en/latest/recommended-packages/) designed for $$\LaTeX$$.

> Interested in taking live notes with LaTeX? Check out [Evan's blog](https://ewpratten.com/blog/notetaking-with-latex/), but brace yourself – the setup gets crazier and involves a fair bit of a learning curve.
{: .prompt-tip}

And that's it! Thanks for reading this blog, I hope this will help you in your future $$\TeX$$nical adventures.
I will wrap this up by showcasing some cool $$\LaTeX$$ applications, with source code.
## $$\LaTeX$$ Gallery
### Math
#### Givens Rotation

$$ { G(i,j,\theta )={\begin{bmatrix}1&\cdots &0&\cdots &0&\cdots &0\\\vdots &\ddots &\vdots &&\vdots &&\vdots \\0&\cdots &\cos{\theta}&\cdots &-\sin{\theta}&\cdots &0\\\vdots &&\vdots &\ddots &\vdots &&\vdots \\0&\cdots &\sin{\theta}&\cdots &\cos{\theta}&\cdots &0\\\vdots &&\vdots &&\vdots &\ddots &\vdots \\0&\cdots &0&\cdots &0&\cdots &1\end{bmatrix}} } $$

<!-- <p style="text-align: center;">\( G(i,j,\theta )\mathbf{x}\) represents a counterclockwise rotation of the vector \(\mathbf{x}\) in the \((i,j)\) plane by \(\theta\) radians</p> -->
<p style="text-align: center;">Apply \( G(i,j,\theta )\) to rotate a vector \( \mathbf{x} \) in the \((i,j)\) plane by \(\theta\) radians (counterclockwise)</p>

{% assign temp_post = site.latex | where: 'name', 'givens-rotation.md' | first %}
```latex
{{ temp_post.content }}
```

#### A remarkable formula of Ramanujan

$$ \sqrt{\frac{\pi e}{2}}= \cfrac{1}{1+{\cfrac{1}{1+{\cfrac{2}{1+{\cfrac{3}{1+{ {\cfrac{4}{1+{_{\ddots }}} }}}}}}}}} + \left\{1 + \dfrac{1}{1\cdot3}+\dfrac{1}{1\cdot3\cdot5}+\dfrac{1}{1\cdot3\cdot5\cdot7}+\dfrac{1}{1\cdot3\cdot5\cdot7\cdot9}+\cdots\right\} $$

{% assign temp_post = site.latex | where: 'name', 'a-remarkable-formula-of-ramanujan.md' | first %}
```latex
{{ temp_post.content }}
```
### Pseudocode using `algorithm2e`
![Random k-SAT problem generation](/random-k-sat-pseudocode-light.svg){: .light w="100%"}
![Random k-SAT problem generation](/random-k-sat-pseudocode-dark.svg){: .dark w="100%"}
_Pseudocode to generate a random $$k$$-SAT problem using `SageMath`_
{% assign temp_post = site.latex | where: 'name', 'pseudocode-using-algorithm2e.md' | first %}
```latex
{{ temp_post.content }}
```
### Code Highlighting using `minted`
![Principal Component Analysis](/principal-component-analysis-light.svg){: .light w="100%"}
![Principal Component Analysis](/principal-component-analysis-dark.svg){: .dark w="100%"}
_Dimensionality Reduction using Principal Component Analysis in `python`_
{% assign temp_post = site.latex | where: 'name', 'code-highlighting-using-minted.md' | first %}
```latex
{{ temp_post.content }}
```
### `TikZ` applications
#### Molecular Orbital Diagrams using `modiagram`
![Molecular Orbital Diagram](/molecular-orbital-diagram-light.svg){: .light w="100%"}
![Molecular Orbital Diagram](/molecular-orbital-diagram-dark.svg){: .dark w="100%"}
_Molecular Orbital Diagram forr Nitric Oxide_
{% assign temp_post = site.latex | where: 'name', 'molecular-orbital-diagrams-using-modiagram.md' | first %}
```latex
{{ temp_post.content }}
```
#### Parse Trees using `tikz-qtree`
![Parse Tree](/parse-tree-light.svg){: .light w="100%"}
![Parse Tree](/parse-tree-dark.svg){: .dark w="100%"}
_Parse Tree for $$ \varphi = (r \rightarrow \neg s) \lor \neg(p \rightarrow (\neg q \lor (r \land (p \rightarrow (s \lor r)))))$$_
{% assign temp_post = site.latex | where: 'name', 'parse-trees-using-tikz-qtree.md' | first %}
```latex
{{ temp_post.content }}
```
#### Electrical Circuits using `circuitikz`
![npn transistor used as an amplifier](/npn-transistor-amplifier-light.svg){: .light w="100%"}
![npn transistor used as an amplifier](/npn-transistor-amplifier-dark.svg){: .dark w="100%"}
_npn transistor used as an amplifier_
{% assign temp_post = site.latex | where: 'name', 'electrical-circuits-using-circuitikz.md' | first %}
```latex
{{ temp_post.content }}
```
### Fitch Proofs using `logicproof`
![Fitch Proofs for Propositional Logic](/fitch-proof-propositional-logic-light.svg){: .light w="100%"}
![Fitch Proofs for Propositional Logic](/fitch-proof-propositional-logic-dark.svg){: .dark w="100%"}
_Fitch Proof of $$\vdash p \rightarrow (q \rightarrow p)$$_

{% assign temp_post = site.latex | where: 'name', 'fitch-proofs-using-logicproof.md' | first %}
```latex
{{ temp_post.content }}
```
## Templates
For the time being, here's my stuff. Feel free to use and tweak them however you like. Maybe I will convert them into templates *someday*.
### Report
[source code](https://github.com/paramrathour/Groebner-Basis-and-Applications/tree/main/Report), [title page](https://tex.stackexchange.com/a/85989)[^showcase]
<div align="center">
	<iframe src='{{ site.url | append: "/Groebner-Basis-and-Applications/Report/main.pdf#view=fitV"}}' align="center" width="60%" height="500px"> </iframe>
</div>

### Slides using `Beamer`
[source code](https://github.com/paramrathour/Groebner-Basis-and-Applications/tree/main/Slides)
<div align="center">
	<iframe src='{{ site.url | append: "/Groebner-Basis-and-Applications/Slides/main.pdf#view=fitH"}}' align="center" width="100%" height="500px"> </iframe> 
</div>
### Resume
[IIT Bombay theme](https://github.com/paramrathour/Resumes/blob/main/Two%20Page.tex), [Generic theme using `moderncv`](https://github.com/paramrathour/Resumes/blob/main/CV.tex)
<div align="center">
	<iframe src='{{ site.url | append: "/Resumes/Two Page.pdf#view=fitV"}}' align="center" width="60%" height="500px"> </iframe>
</div>

## References
[^texbook]: Donald E. Knuth, "The $$\TeX$$book"
[^ctan]: ["Comprehensive $$\TeX$$ Archive Network"](https://www.ctan.org/pkg)
[^showcase]: [$$\TeX$$ - $$\LaTeX$$ Stack Exchange, "Showcase of beautiful typography done in $$\TeX$$"](https://tex.stackexchange.com/questions/1319/showcase-of-beautiful-typography-done-in-tex-friends)