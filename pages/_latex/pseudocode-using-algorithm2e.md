---
---
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