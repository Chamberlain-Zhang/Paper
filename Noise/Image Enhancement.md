# Image Enhancement



#### *From Fidelity to Perceptual Quality: A Semi-Supervised Approach for Low-Light Image Enhancement*

This paper use adversarial network and unpaired dataset to make enhanced image have high-quality which is preferred by human vision.  The loss function of generator is composed of SSIM、Perception and Adversarial Loss.



#### Zero-Reference Deep Curve Estimation for Low-Light Image Enhancement

This paper use network to estimate pixel-wise parameters of mapping function (Light Enhancement Curve) which mapping low-light image to ordinary light. With special designed loss function, the network can be optimized without target image and adversarial training strategies. 

The light enhancement curve is designed as quadratic function,  which can be expressed as:
$$
\begin{equation}
f(x) = x + \alpha x(1-x)
\end{equation} \label{base function}
$$
The network generate several parameter groups which can be used to imitate high-order curves by applying Euq. $\eqref{base function}$ iteratively. Specifically,
$$
\begin{equation}
g(x) = f(x) + \alpha f(x)\left(1-f(x)\right)
\end{equation} \label{high order function}
$$
 **Non-Reference Loss Function:**

![](https://li-chongyi.github.io/Zero-DCE_files/loss.png)

Ablation study of the contribution of each loss (spatial consistency loss *Lspa*, exposure control loss *Lexp*, color constancy loss *Lcol*, illumination smoothness loss *LtvA*).

1. *Spatial Consistency Loss* : 
   $$
   \begin{equation}
   L_{spatial \ consistency} = \frac1K \sum_{i=1}^{K} \sum_{j \in \Omega(i)} \left(|T_{i}-T_{j}| - |O_{i}-O_{j}|  \right) ^2
   \end{equation} \label{spatial consistency loss}
   $$
   where $K$ is the number of local region, and $\Omega(i)$ is the four neighboring regions (top, down, left, right) centered as the region $i$.

   ==*Contrast Consistency Loss (provided by myself)*== : 
   $$
   \begin{equation}
   L_{spatial \ consistency} = \frac1K \sum_{i=1}^{K} \sum_{j \in \Omega(i)} \left(Sgn(T_{i}-T_{j}) - Sgn(O_{i}-O_{j})  \right)
   \end{equation} \label{contrast consistency loss}
   $$
   where $K$ is the number of local region, and $\Omega(i)$ is the four neighboring regions (top, down, left, right) centered as the region $i$.

   

2. *Exposure Control Loss*:
   $$
   \begin{equation}
   L_{exposure} = \frac1M \sum_{k=1}^{M} |\overline O_{k}-E|
   \end{equation} \label{exposure control}
   $$
   where $M$ represents the number of non-overlapping local region of size $16\times16$ , $\overline O_k$ is the average intensity value of a local region in the enhanced image. We set E to 0.6 in our experiments although we do not find much performance difference by setting E within [0.4, 0.7].



3. ==*Color Constancy Loss (need extended readings):*==

   Following [Gray-World color constancy hypothesis](Gershon Buchsbaum. A spatial processor model for object colour perception. J. Franklin Institute, 310(1):1–26, 1980.[) that color in each sensor channel averages to gray over the entire image, we design a color constancy loss to correct the potential color deviations in the enhanced image and also build the relations among the three adjusted channels. The color constancy loss $L_{color}$ can be expressed as:
   $$
   \begin{equation}
   L_{color} = \sum_{\forall (p,q)\in\Theta}(J^{p}-J^{q})^2,\ \Theta=\{ (R,G),(R,B),(G,B)\}
   \end{equation} \label{color constancy}
   $$
   

4. *Illumination Smoothness Loss (total variation)*

   

   

   

   

   
