---
---
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