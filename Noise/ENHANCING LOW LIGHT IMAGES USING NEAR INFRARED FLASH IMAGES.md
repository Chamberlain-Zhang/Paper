# ENHANCING LOW LIGHT IMAGES USING NEAR INFRARED FLASH IMAGES

<p align='center'> IEEE International Conference on Image Processing</p>

## Denoising
Our visible ambient image denoising builds on [weighted least squares (WLS) smoothing](https://en.wikipedia.org/wiki/Weighted_least_squares).
Given an image $V$, the WLS smoothing seeks a new image $V^{b}$, which is as close as possible to $V$, 
and is also as smooth as possible everywhere except at significant gradient locations in $V$.
Formally, $V^{b}$ can be expressed as
$$
\eqalignno{V^{b}=\arg_{V^{b}}\min
\sum_{p}((V_{p}^{b}-V_{p})^{2}+\lambda(a_{x,p}({\partial V^{b}\over
\partial x})_ {p}^{2}+a_{y,p}({\partial V^{b}\over \partial y})_ {p}^{2})), \hbox{(1)}}
$$

where the subscript $p$ denotes the pixel location and $\lambda$ balances between the two terms. 
For normal WLS smoothing, the spatially varying smoothness weights $a_{x,p}$ and $a_{y,p}$ are defined as follows:

$$
\eqalignno{a_{x,p}^{b}=(\vert {\partial\log(V)\over \partial x}\vert _ {p}^{\alpha}+\epsilon)^{-1},\cr
a_{y,p}^{b}=(\vert {\partial\log(V)\over \partial y}\vert
_ {p}^{\alpha}+\epsilon)^{-1},  &\hbox{(2)}}
$$

where $\epsilon$ is a small constant (*typically 0.0001*) to avoid division by zero. $\alpha$ controls the sensitivity to gradients of $V$.
Typically, its value ranges between *1.2 and 2.0*.

***We apply the normal WLS smoothing to $V^b$ in each RGB color channel. The value of λ depends on the noise level of the image V.
For a higher noise level, λ is set larger.*** Using normal WLS smoothing, we can remove the noise in visible image V to some extend.
However, as the noise level varies in different regions of the image, some regions may be over-smoothened.


The NIR flash image $N$ contains the same image structure with the visible image and it is not contaminated by noise. 
Thus, we can use it to guide the smoothing to avoid over/under-smoothing.
However, as different materials have different reflectivity to visible and NIR light, 
some edges in V may disappear in N, which leads to edge blur in smoothing results. 
However, those edges, especially the strong edges, can be found in Vb. Hence, 
we use the information from both Vb and N to perform the smoothing.

The image $N$ is monochromic and contains no color information. 
Therefore, we convert image $V$ from RGB color space to YIQ color space and denote its intensity (Y channel) and color components (I and Q channels) as $V_{I}$ and $V_{C}$. 
Similarly, we denote the intensity and color components of image $V_{b}$ as $V^b_I$ and $V^b_C$. We extend the normal WLS smooting and apply it on $V_{I}$. 
The new smoothing has the same form with Equ.1. We combine the gradients of $V^b_I$ and $N$, then define the new smoothness weights as,

$$
\eqalignno{&a_{x,p}^{nr}=(\vert {\partial\log(N)\over \partial
x}\cdot{\partial log(V_{I}^{b})\over\partial x}\vert
^{\alpha}+\epsilon)^{-1},\cr &a_{y,p}^{nr}=(\vert {\partial\log(N)\over \partial y}\cdot{\partial log(V_{I}^{b})\over \partial y}\vert ^{\alpha}+\epsilon)^{-1}, &\hbox{(3)}}
$$

where $\vert \cdot \vert$ denotes scalar multiplication. Because the smoothing uses the information from both V and N, we call it dual WLS smoothing. 
The output of dual WLS smoothing is the noise reduced intensity component of the visible image, denoted by $V^{nr}_I $.







