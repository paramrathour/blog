---
title: "Code Highlighting using 'minted'"
---
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