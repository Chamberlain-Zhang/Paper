# ENHANCING LOW LIGHT IMAGES USING NEAR INFRARED FLASH IMAGES

<p align='center'> IEEE International Conference on Image Processing</p>

## Denoising
Our visible ambient image denoising builds on [weighted least squares (WLS) smoothing](https://en.wikipedia.org/wiki/Weighted_least_squares).
Given an image $V$, the WLS smoothing seeks a new image $V^{b}$, which is as close as possible to $V$, 
and is also as smooth as possible everywhere except at significant gradient locations in $V$.
Formally, $V^{b}$ can be expressed as
$$
V^{b}=\arg_{V^{b}}\min
\sum_{p}((V_{p}^{b}-V_{p})^{2}+\lambda(a_{x,p}({\partial V^{b}\over
\partial x})_ {p}^{2}+a_{y,p}({\partial V^{b}\over \partial y})_ {p}^{2}))
$$

where the subscript $p$ denotes the pixel location and $\lambda$ balances between the two terms. 
For normal WLS smoothing, the spatially varying smoothness weights $a_{x,p}$ and $a_{y,p}$ are defined as follows:

$$
\eqalignno{a_{x,p}^{b}=(\vert {\partial\log(V)\over \partial x}\vert _ {p}^{\alpha}+\epsilon)^{-1},\cr
a_{y,p}^{b}=(\vert {\partial\log(V)\over \partial y}\vert
_ {p}^{\alpha}+\epsilon)^{-1},}
$$

where $\epsilon$ is a small constant (typically 0.0001) to avoid division by zero. $\alpha$ controls the sensitivity to gradients of $V$.
Typically, its value ranges between 1.2 and 2.0.
