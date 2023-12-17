---
layout: post
title: LaTeX Tips
description: "Newbie's roadmap: getting started with resources to the ultimate setup!"
categories: [Programming, Tutorial]
tags: [latex, programming, tutorial]
math: true
pin: true
date: 2023-12-17 08:21 +0530
---
## History
While working on his magnum opus, 'The Art of Computer Programming', Donald Knuth was disappointed with the quality typesetting which led him to develop $$\TeX$$, a typesetting system intended for the creation of beautiful books that contain a lot of mathematics[^texbook]. With Leslie Lamport's modifications, $$\LaTeX$$ was born.

## Features
Unlike a <span data-bs-toggle="tooltip" data-bs-placement="top" title="What You See Is What You Get">WYSIWYG</span> software, here an individual writes code and the document is generated automatically. This allows users to focus on writing actual content while the software takes care of text formatting and document layout.

Here are some of its advantages
- Support for complex math expressions and enviroments
- Automatic numbering and generation of table of contents, citations and other lists 
- Active open-source community has developed packages[^ctan] for pretty much everything

## Getting Started
You really don't need to know anything else about it.

You can use [Overleaf](https://www.overleaf.com?r=8d4792b1&rm=d&rs=b) to start your $$\LaTeX$$ journey. The [Learn LaTeX in 30 minutes](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes) blog will explain you the basics. And that's it! You can now use overleaf to work on any document.

### Resources
- [LaTeX Course by Learner's Space, IIT Bombay](https://github.com/paramrathour/LaTeX) - A concise course that covers pretty much all the basics and gives you a flavour of advance stuff.
- [LaTeX Tutorial](https://latex-tutorial.com/tutorials) - Short and sweet tutorials covering various $$\TeX$$nical concepts. This is from where I learnt but the [Overleaf tutorials](https://www.overleaf.com/learn) and guides are also good.
- [$$\LaTeX$$ in 24 Hours](https://link.springer.com/book/10.1007/978-3-319-47831-9) - This book is an overkill, but this really shows off what $$\LaTeX$$ can do.
- [The $$\TeX$$book](https://ctan.org/pkg/texbook?lang=en) - The book by the creator himself is like an overkill on steroids, if that makes sense.
- [Comprehensive $$\TeX$$ Archive Network](https://ctan.org/) (CTAN) - The holy documentation, something everyone should read at some point in their life, right?
- [Awesome LaTeX](https://github.com/egeerardyn/awesome-LaTeX) - A list of list of awesome $$\LaTeX$$ things.

> Also, do check out this [tutorial](https://aryamanmaithani.github.io/latex/) by Aryaman Maithani, especially the "things to keep in mind" section to learn it the correct way. He's the guy who inspired me to delve into $$\LaTeX$$.
{: .prompt-tip}

These resources are handy, but if you ever get stuck, just Google it, and you'll get what you want.\
Trust me, the [$$\TeX$$ - $$\LaTeX$$ Stack Exchange](https://tex.stackexchange.com/) is a lifesaver for literally any $$\TeX$$nical doubt.

#### Online Tools
- [Detexify](http://detexify.kirelabs.org/classify.html) - Recognises hand-drawn symbols and it provides the corresponding $$\LaTeX$$ command and packages to import if any.

Just to make it clear, if coding something gets too complex, you can always turn to online GUI tools such as
- [Table Generator](https://www.tablesgenerator.com/) - Helpful for messy tables with merged cells and custom borders.
- [Finite State Machine Designer](https://madebyevan.com/fsm/)

and many more!

## Offline Setup
Once you get a good grasp with $$\LaTeX$$, go for an offline setup.

I use Sublime Text with `LaTeXTools` and `LaTeXYZ` packages to speed up writing program.
![sublime-text-latex-math-render](/sublime-text-latex-math-render.gif){: w="100%"}
_Gaussian function of a normally distributed random variable with expected value $$=\mu$$ and standard deviation $$=\sigma$$_
### Features
- Keyboard Shortcuts
- Autocompletions and Automatching
- Equation and Image Preview
- Forward Search and Inverse Search
- Spell Checking
- Custom Builders and many more

For this, you need to follow the steps mentioned in this blog, [Set up Sublime Text as Your Ultimate LaTeX Editor](https://jdhao.github.io/2018/03/10/sublime-text-latextools-setup/).
I have summarized important points below.

### Installation
- LaTeX - either [TeX Live](https://www.tug.org/texlive/acquire.html) or [MikTeX](https://miktex.org/) works
- [Sublime Text](https://www.sublimetext.com/download) - A light-weight but powerful text editor with support for many programming languages.
	- [Package Control](https://packagecontrol.io/installation)
		- [`LaTeXTools`](https://packagecontrol.io/packages/LaTeXTools)
		- [`LaTeXYZ`](https://packagecontrol.io/packages/LaTeXYZ)
		- [`LaTeX-cwl`](https://packagecontrol.io/packages/LaTeX-cwl)
- [Sumatra PDF Viewer](https://www.sumatrapdfreader.org/download-free-pdf-viewer) - A superfast and light-weight `pdf` viewer which also supports `epub`, `djvu`, `mobi`, `cbz` and many other document formats with customizable [keyboard shortcuts](https://www.sumatrapdfreader.org/docs/SumatraPDF-documentation).

### Configuration Steps
- [Configure Inverse Search](https://jdhao.github.io/2018/03/10/sublime-text-latextools-setup/#configure-inverse-search-for-pdf-files)
- Check out keyboard shortcuts for [`LaTeXTools`](https://latextools.readthedocs.io/en/latest/keybindings/) and [`LaTeXYZ`](https://packagecontrol.io/packages/LaTeXYZ)
- Fix [new window open](https://github.com/SublimeText/LaTeXTools/issues/1506) and [autocomplete](https://github.com/SublimeText/LaTeXTools/issues/1506) problem if it occurs.
- Optionally, install more [recommended packages](https://latextools.readthedocs.io/en/latest/recommended-packages/) designed for $$\LaTeX$$.

> Interested in taking live notes with LaTeX? Check out [Evan's blog](https://ewpratten.com/blog/notetaking-with-latex/) is , but brace yourself – the setup gets crazier and it involves a fair bit of the learning curve.
{: .prompt-tip}

And that's it! Thanks for reading this blog, I hope this will help you in your future $$\TeX$$nical adventures.
I will wrap this up with showcasing some cool $$\LaTeX$$ uses with code.
## LaTeX Gallery
### Math
#### Givens Rotation

$$ { G(i,j,\theta )={\begin{bmatrix}1&\cdots &0&\cdots &0&\cdots &0\\\vdots &\ddots &\vdots &&\vdots &&\vdots \\0&\cdots &\cos{\theta}&\cdots &-\sin{\theta}&\cdots &0\\\vdots &&\vdots &\ddots &\vdots &&\vdots \\0&\cdots &\sin{\theta}&\cdots &\cos{\theta}&\cdots &0\\\vdots &&\vdots &&\vdots &\ddots &\vdots \\0&\cdots &0&\cdots &0&\cdots &1\end{bmatrix}} } $$

<!-- <p style="text-align: center;">\( G(i,j,\theta )\mathbf{x}\) represents a counterclockwise rotation of the vector \(\mathbf{x}\) in the \((i,j)\) plane by \(\theta\) radians</p> -->
<p style="text-align: center;">Apply \( G(i,j,\theta )\) to rotate a vector \( \mathbf{x} \) in the \((i,j)\) plane by \(\theta\) radians (counterclockwise)</p>

```tex
\begin{equation}
  G(i,j,\theta )={
    \begin{bmatrix}
    1&\cdots &0&\cdots &0&\cdots &0\\
    \vdots &\ddots &\vdots &&\vdots &&\vdots \\
    0&\cdots &\cos{\theta}&\cdots &-\sin{\theta}&\cdots &0\\
    \vdots &&\vdots &\ddots &\vdots &&\vdots \\
    0&\cdots &\sin{\theta}&\cdots &\cos{\theta}&\cdots &0\\
    \vdots &&\vdots &&\vdots &\ddots &\vdots \\
    0&\cdots &0&\cdots &0&\cdots &1
    \end{bmatrix}
    }
\end{equation}
```

#### A remarkable formula of Ramanujan

$$ \sqrt{\frac{\pi e}{2}}= \cfrac{1}{1+{\cfrac{1}{1+{\cfrac{2}{1+{\cfrac{3}{1+{ {\cfrac{4}{1+{_{\ddots }}} }}}}}}}}} + \left\{1 + \dfrac{1}{1\cdot3}+\dfrac{1}{1\cdot3\cdot5}+\dfrac{1}{1\cdot3\cdot5\cdot7}+\dfrac{1}{1\cdot3\cdot5\cdot7\cdot9}+\cdots\right\} $$

```tex
\begin{equation}
  \sqrt{\frac{\pi e}{2}}= \cfrac{1}{1+{\cfrac{1}{1+{\cfrac{2}{1+{\cfrac{3}{1+{ {\cfrac{4}{1+{_{\ddots }}} }}}}}}}}} + \left\{1 
  + 
  \dfrac{1}{1\cdot3}+\dfrac{1}{1\cdot3\cdot5}+\dfrac{1}{1\cdot3\cdot5\cdot7}+\dfrac{1}{1\cdot3\cdot5\cdot7\cdot9}+\cdots\right\}
\end{equation}
```
### Pseudocodes using `algorithm2e`
![Random k-SAT problem generation](/random-k-sat-pseudocode-light.svg){: .light w="100%"}
![Random k-SAT problem generation](/random-k-sat-pseudocode-dark.svg){: .dark w="100%"}
_Pseudocode to generate a random $$k$$-SAT problem using `SageMath`_
```tex
\usepackage[linesnumbered,ruled,vlined]{algorithm2e}

\begin{algorithm}[H]
\SetArgSty{textrm}
\SetCommentSty{emph}
\SetKwInOut{Input}{Input}
\SetKwInOut{Output}{Output}
\underline{Function \texttt{random\_k\_SAT}} ($k$, $n$, $m$ (\texttt{NUMBER\_OF\_CLAUSES}))\;
\Input{$n=$ number of variables and $m=$ number of clauses, $n\leq m$}
\Output{$n$ variables, $m$ clauses in the generated $n$ variables}
\caption{Generate random $k$-SAT}
\Begin{
Create $n$ variables $x_1, x_2,\ldots, x_n$ representing each as a string\;
Create $m$ clauses $C_1, C_2, \ldots, C_{m}$ as empty strings\;
\For{each clause $C_i$}{ %$i\in\{0,1,\ldots,m-1\}$
    Sample $k$ random variables from $x_1,\ldots, x_{n}$ (and sort them)\;
    These are called \texttt{chosen\_variables} $= [x_{i_1}, \ldots, x_{i_k}]$\ ($i_1 < \ldots < i_k$)\;
    \While{True}{
        Randomly generate $k$ \texttt{coefficients} = [$c_1,\ldots, c_k$] where each $c_i\in\{-1,0,1\}$\;
        \tcp{where $c_i$ is the coefficient of $x_{i_k}$}
        \tcp{Exclude the case when all coefficients are zero; i.e., the clause is empty}
        \If{$\exists  i$ such that $c_i\neq 0$}{
            break\;
        }
    }
    \For{each non-empty coefficient $c_i$ in \texttt{coefficients}}{
        \If{$c_i = -1$}{
            Append `$\sim x_{i_k}$' to $C_i$\;
        }
        \If{$c_i = 1$}{
            Append `$x_{i_k}$' to $C_i$\;
        }
        \If{there are more non-empty coefficients}{
            Append `$\mid$' to $C_i$\;
        }
    }
    \tcp{Finally, convert the clause into propositional formula using SageMath}
    $C_i= $\texttt{ sage.logic.propcalc.formula}$(C_i)$\;
}
\Return [$x_1, x_2,\ldots, x_n$], [$C_1, C_2, \ldots, C_{m}$]
}
\end{algorithm}
```
### Code Highlighting using `minted`
![Principal Component Analysis](/principal-component-analysis-light.svg){: .light w="100%"}
![Principal Component Analysis](/principal-component-analysis-dark.svg){: .dark w="100%"}
_Dimensionality Reduction using Principal Component Analysis in `python`_
```tex
\usepackage{minted}

\begin{minted}[frame = single, breaklines, linenos]{python}
import numpy as np

def PCA(datapoints, PCA_THRESHOLD):
    mean = np.mean(datapoints, axis = 1)
    datapoints = datapoints - mean.reshape((datapoints.shape[0], 1))
    L = datapoints.T @ datapoints
    eigenvalues, eigenvectors = np.linalg.eigh(L)
    eigenvalues = eigenvalues[::-1]
    eigenvectors = eigenvectors[:, ::-1]
    num_components = np.searchsorted(np.cumsum(eigenvalues) / np.sum(eigenvalues), PCA_THRESHOLD, side = "left") + 1
    eigenvectors = datapoints @ eigenvectors[:,:num_components]
    eigenvectors = eigenvectors / np.linalg.norm(eigenvectors, axis = 0)
    eigenvalues = eigenvalues[:num_components]
    return eigenvalues, eigenvectors, mean
\end{minted}
```
### `TikZ` applications
#### Molecular Orbital Diagrams using `modiagram`
![Molecular Orbital Diagram](/molecular-orbital-diagram-light.svg){: .light w="100%"}
![Molecular Orbital Diagram](/molecular-orbital-diagram-dark.svg){: .dark w="100%"}
_Molecular Orbital Diagram forr Nitric Oxide_
```tex
\usepackage{modiagram}

\begin{modiagram}[labels,names]
  \atom[N]{left}{ 2p = {0;up,up,up} }
  \atom[O]{right}{ 2p = {2;pair,up,up} }
  \molecule[NO]{
    2pMO = {1.8,.4;pair,pair,pair,up},
  }
\end{modiagram}
```
#### Parse Trees using `tikz-qtree`
![Parse Tree](/parse-tree-light.svg){: .light w="100%"}
![Parse Tree](/parse-tree-dark.svg){: .dark w="100%"}
_Parse Tree for $$ \varphi = (r \rightarrow \neg s) \lor \neg(p \rightarrow (\neg q \lor (r \land (p \rightarrow (s \lor r)))))$$_
```tex
\usepackage{tikz-qtree}
\tikzset{edge from parent/.style={draw, edge from parent path={(\tikzparentnode) -- (\tikzchildnode)}}}

\begin{tikzpicture}[every node/.style={draw,circle,minimum width={1em}},level distance=3.5em,sibling distance=3em]
    \Tree
     [.$\lor$
        [.$\rightarrow$  $r$
            [.$\neg$ $s$ ]] 
        [.$\neg$ [.$\rightarrow$ $p$ [.$\lor$ [.$\neg$ $q$
        ]
        [.$\land$  $r$
            [.$\rightarrow$ $p$ [.$\lor$ $s$ $r$ ]]] 
         ] ]
        ]]
\end{tikzpicture}
```
#### Electrical Circuits using `circuitikz`
![npn transistor used as an amplifier](/npn-transistor-amplifier-light.svg){: .light w="100%"}
![npn transistor used as an amplifier](/npn-transistor-amplifier-dark.svg){: .dark w="100%"}
_npn transistor used as an amplifier_
```tex
\usepackage{circuitikz}

\begin{circuitikz}[american voltages]
\draw 
(0,0) to [short,o-,C,l=$C_1$] (2,0)
to [R, l_=$R_1$] (2,3)
to [short,-o] (9,3)
to [open,v^>=$V_{CC}$] (9,-3);
\draw 
(0,-3) to [short,o-*] (2,-3)
to [short,-*] (4,-3)
to [short,-*] (6,-3)
to [short] (8,-3)
to [short,o-o] (9,-3);
\draw 
(6,-3) to[short] node[ground] {} (6,-3.5);
\draw 
(2,0) to [R, l_=$R_2$] [v^>=$V_B$] (2,-3);
\draw
(0,0) to [open,v^>=$V_0\sin(\omega t)$] (0,-3);
\draw 
(4,0) node[npn](npn) {}
(npn.base) node[anchor=north,xshift=0.5em] {B}
(npn.collector) node[anchor=north,xshift=-0.5em,yshift=0.3em] {C}
(npn.emitter) node[anchor=south,xshift=-0.5em,yshift=-0.4em] {E};
\draw 
(2,0) to [short,i=$i_B$] (3.2,0);
\draw
(4,3) to [R,l_=$R_L$,i=$i_C$,*-*] (4,0.8)
to [short,-o] (8,0.8)
to [open,v^>=$V_{out}$] (8,-3);
\draw 
(4,-0.75) to [short,i=$i_E$] (4,-1.5)
to [R,l_=$R_E$] [v^>=$V_E$] (4,-3);
\draw 
(4,-1.5) to [short] (6,-1.5)
to [C,l_=$C_2$] (6,-3);
\draw 
(4.4,0.8) to [open,v^>=$V_{CE}$] (4.4,-0.8);
\end{circuitikz}
```
### Fitch Proofs using `logicproof`
![Fitch Proofs for Propositional Logic](/fitch-proof-propositional-logic-light.svg){: .light w="100%"}
![Fitch Proofs for Propositional Logic](/fitch-proof-propositional-logic-dark.svg){: .dark w="100%"}
_Fitch Proof of $$\vdash p \rightarrow (q \rightarrow p)$$_
```tex
\usepackage{logicproof}

\begin{logicproof}{4}
p \lor \neg p & LEM on $p$\\
\begin{subproof}
    p & assumption\\
    q \lor \neg q & LEM on $q$\\
    \begin{subproof}
        q & assumption\\
        \begin{subproof}
            p & copy 2\\
            \begin{subproof}
                q & copy 4\\
                p & copy 2
            \end{subproof}
            q \rightarrow p & $\rightarrow$i 6--7
        \end{subproof}
        p \rightarrow (q \rightarrow p) & $\rightarrow$i 5--8
    \end{subproof}
    \begin{subproof}
        \neg q & assumption\\
        \begin{subproof}
            p & copy 2\\
            \begin{subproof}
                q & assumption\\
                p & copy 2
            \end{subproof}
            q \rightarrow p & $\rightarrow$i 12--13
        \end{subproof}
        p \rightarrow (q \rightarrow p) & $\rightarrow$i 11--14
    \end{subproof}
    p \rightarrow (q \rightarrow p) & $\lor$e 3, 4--9, 8--15
\end{subproof}
\begin{subproof}
    \neg p & assumption\\
    q \lor \neg q & LEM on $q$\\
    \begin{subproof}
        q & assumption\\
        \begin{subproof}
            p & assumption\\
            \neg p & copy 17\\
            \bot & $\bot$i 20,21\\
            q \rightarrow p & $\bot$e 22
        \end{subproof}
        p \rightarrow (q \rightarrow p) & $\rightarrow$i 20--23
    \end{subproof}
    \begin{subproof}
        \neg q & assumption\\
        \begin{subproof}
            p & assumption\\
            \neg p & copy 17\\
            \bot & $\bot$i 26,27\\
            q \rightarrow p & $\bot$e 28
        \end{subproof}
        p \rightarrow (q \rightarrow p) & $\rightarrow$i 26--29
    \end{subproof}
    p \rightarrow (q \rightarrow p) & $\lor$e 18, 19--24, 25--30
\end{subproof}
p \rightarrow (q \rightarrow p) & $\lor$e 1, 2--16, 17--31
\end{logicproof}
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
[IIT Bombay theme](https://github.com/paramrathour/Resumes/blob/main/Two Page.tex), [Generic theme using `moderncv`](https://github.com/paramrathour/Resumes/blob/main/CV.tex)
<div align="center">
	<iframe src='{{ site.url | append: "/Resumes/Two Page.pdf#view=fitV"}}' align="center" width="60%" height="500px"> </iframe>
</div>

## References
[^texbook]: Donald E. Knuth, "The $$\TeX$$book"
[^ctan]: ["Comprehensive $$\TeX$$ Archive Network"](https://www.ctan.org/pkg)
[^showcase]: [$$\TeX$$ - $$\LaTeX$$ Stack Exchange, "Showcase of beautiful typography done in $$\TeX$$"](https://tex.stackexchange.com/questions/1319/showcase-of-beautiful-typography-done-in-tex-friends)