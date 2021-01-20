# Some Interesting Loss Function

### The Log Loss Function

$$
\begin{equation}
L(x, \hat x) = || log(max(x, \epsilon)) - log(max(\hat x, \epsilon))||_ {1\ or\ 2}
\end{equation}
$$

where $\epsilon$ is a small constant for numerical stability, and $x$ and $\hat x$ are input and output respectively.
The log loss term is used for highlighting the difference between input and output.
