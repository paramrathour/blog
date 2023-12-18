---
---
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