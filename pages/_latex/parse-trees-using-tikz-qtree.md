---
title: "Parse Trees using 'tikz-qtree'"
---
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