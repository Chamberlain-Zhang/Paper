# [Variance-stabilizing transformation](https://en.wikipedia.org/wiki/Variance-stabilizing_transformation)

[Model-based variance-stabilizing transformation for Illumina microarray data](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2241869/#B7)

[Optimal Inversion of the Generalized Anscombe Transformation for Poisson-Gaussian Noise](https://ieeexplore.ieee.org/document/6212354)


## The Noise Model

> ![](https://www.researchgate.net/publication/344662685/figure/fig2/AS:946740739977216@1602731990078/Photon-transfer-pipeline-multiple-noise-sources-like-shot-noise-read-out-noise-and.png "Fig.1 Photon transfer pipeline: multiple noise sources like shot noise, read-out noise and thermal noise are involved along the camera pipeline.")

> *Fig.1 Photon transfer pipeline: multiple noise sources like shot noise, read-out noise and thermal noise are involved along the camera pipeline.*


A camera sensor converts the photons hitting the pixel area during the exposure time into a digitized luminance map.
As shown in the photon transfer pipeline shown in Fig. 1, this process contains multiple stages, where each stage introduces speciﬁc noise. 
Let us ﬁrst consider an ideal system with no noise. Under the linear camera model, at each pixel, the sensor conversion is a linear ampliﬁcation as: 

$$
\begin{equation}
x^\ast = g\alpha u^\ast
\end{equation}
$$

where $u^\ast$ is the expected number of photons hitting the pixel area, $\alpha$ is the quantum eﬃciency factor and $g$ is the analog gain.
Now considering the system noise in each step of the pipeline in Fig. 1, we have:

$$
\begin{equation}
x = g(\alpha u + n_d) + n_r
\end{equation}
$$

where $u$ denotes the actual collected amount of photons, and $n_d \sim \mathcal N(\theta,\delta^2_d)$ and $n_r \sim \mathcal N(\theta,\delta^2_r)$ are Gaussian noise before and after applying the analog gain. Furthermore, it is demonstrated in [14] that $u$ obeys a Poisson distribution of $u^\ast$, given by 

$$
\begin{equation}
u \sim \mathcal P(u^\ast)
\end{equation}
$$

Combining Eqn. (1) to Eqn. (3), we have:

$$
\begin{equation}
{x\sim(g\alpha)\mathcal P(\frac{x^\ast}{g\alpha})+\mathcal N(0, g^2 \delta^2_d + \delta^2_r)}
\end{equation}
$$

This is consistent with the Poisson-Gaussian noise model that has been extensively studied in previous work [16,27].
This formulation can be further simpliﬁed by replacing $k=g\alpha$ and $\delta^2=g^2 \delta^2_d + \delta^2_r$ :

$$
\begin{equation}
{x\sim k\mathcal P(\frac{x^\ast}{k})+\mathcal N(0, \delta^2)}
\end{equation}
$$

Note that both $k$ and $\delta^2$ are related to $g$, which is determined by the ISO setting of the camera.

