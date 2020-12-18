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

where u∗ is the expected number of photons hitting the pixel area, α is the quantum eﬃciency factor and g is the analog gain.
Now considering the system noise in each step of the pipeline in Fig. 1, we have:

