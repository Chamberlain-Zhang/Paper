# [Variance-stabilizing transformation](https://en.wikipedia.org/wiki/Variance-stabilizing_transformation)

[Model-based variance-stabilizing transformation for Illumina microarray data](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2241869/#B7)

[Optimal Inversion of the Generalized Anscombe Transformation for Poisson-Gaussian Noise](https://ieeexplore.ieee.org/document/6212354)



## [1. Poisson distribution](https://brilliant.org/wiki/poisson-distribution/#:~:text=The%20Poisson%20distribution%20is%20the,the%20drive%2Dthrough%20per%20minute.)

The **Poisson distribution** is the [discrete probability distribution](https://brilliant.org/wiki/discrete-random-variables-definition/) of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

>A certain fast-food restaurant gets an average of 3 visitors to the drive-through per minute. This is just an average, however. The actual amount can vary.
>
>A Poisson distribution can be used to analyze the probability of various events regarding how many customers go through the drive-through. It can allow one to calculate the probability of a lull in activity (when there are 0 customers coming to the drive-through) as well as the probability of a flurry of activity (when there are 5 or more customers coming to the drive-through). This information can, in turn, help a manager plan for these events with staffing and scheduling.

In addition to its use for staffing and scheduling, the Poisson distribution also has applications in biology (especially [mutation](https://brilliant.org/wiki/mutation-and-dna-repair/) detection), finance, disaster readiness, and any other situation in which events are time-independent.

#### 1.1 Conditions for Using Poisson distribution

The Poisson distribution is applicable only when several conditions hold.

> **Conditions for Poisson Distribution:**
>
> - An event can occur any number of times during a time period.
> - Events occur independently. In other words, if an event occurs, it does not affect the probability of another event occurring in the same time period.
> - The rate of occurrence is constant; that is, the rate does not change based on time.
> - The probability of an event occurring is proportional to the length of the time period. For example, it should be twice as likely for an event to occur in a 2 hour time period than it is for an event to occur in a 1 hour period.



#### 1.2 Properties of the Poisson Distribution

The [expected value](https://brilliant.org/wiki/expected-value/) of a Poisson distribution should come as no surprise, as each Poisson distribution is defined by its expected value.

> **Expected Value of Poisson Random Variable:**
>
> Given a discrete random variable $X$ that follows a Poisson distribution with parameter $\lambda$, the expected value of this variable is
> $$
> \begin{equation}
> \text{E}[X]=\lambda.
> \end{equation}
> $$

> By the definition of [expected value](https://brilliant.org/wiki/expected-value-definition/),
> $$
> \begin{equation}
> \text{E}[X] = \sum_{x \in \text{Im}(X)}xP(X=x)
> \end{equation}
> $$
> where $x \in \text{Im}(X)$ simply means that $x$ is one of the possible values of the [random variable](https://brilliant.org/wiki/discrete-random-variables-definition/) $X$. Applying this to the Poisson distribution,
> $$
> \begin{equation}
> {
> \begin{aligned} \text{E}[X] &= \sum_{k = 0}^{\infty} k \cdot \frac{\lambda^ke^{-\lambda}}{k!} \\ &=\lambda e^{-\lambda}\sum_{k=1}^{\infty} \frac{\lambda^{k-1}}{(k-1)!} \\ &=\lambda e^{-\lambda}\sum_{j=0}^{\infty} \frac{\lambda^j}{j!} \\ &=\lambda e^{-\lambda}e^{\lambda} \\ &=\lambda, 
> \end{aligned}
> }
> \end{equation}
> $$
> where the rescaling $j=k-1$ and the [Taylor series](https://brilliant.org/wiki/taylor-series/) $e^x=\sum_{k=0}^{\infty}\frac{x^k}{k!}$ was used.

The [variance](https://brilliant.org/wiki/variance-definition/) of the Poisson distribution is also conveniently simple.

> **Variance of Poisson Random Variable:**
>
> Given a discrete random variable$ X$ that follows a Poisson distribution with parameter$ \lambda$, the variance of this variable is
> $$
> \begin{equation}
> \text{Var}[X]=\lambda.
> \end{equation}
> $$

> The proof involves the routine (but computationally intensive) calculation that $E[X^2]=\lambda^2+\lambda$. Then using the formula for [variance](https://brilliant.org/wiki/variance-properties/)
> $$
> \begin{equation}
> \text{Var}[X] = E[X^2]-E[X]^2,
> \end{equation}
> $$
> we have$ \text{Var}[X]=\lambda^2+\lambda-\lambda^2=\lambda$.





## [2. The Noise Model](Practical Deep Raw Image Denoising on Mobile Devices)

> ![](https://www.researchgate.net/publication/344662685/figure/fig2/AS:946740739977216@1602731990078/Photon-transfer-pipeline-multiple-noise-sources-like-shot-noise-read-out-noise-and.png "Fig.1 Photon transfer pipeline: multiple noise sources like shot noise, read-out noise and thermal noise are involved along the camera pipeline.")

> **Fig.1** *Photon transfer pipeline: multiple noise sources like shot noise, read-out noise and thermal noise are involved along the camera pipeline.*


A camera sensor converts the photons hitting the pixel area during the exposure time into a digitized luminance map. As shown in the photon transfer pipeline shown in Fig. 1, this process contains multiple stages, where each stage introduces speciﬁc noise.  Let us ﬁrst consider an ideal system with no noise. Under the linear camera model, at each pixel, the sensor conversion is a linear ampliﬁcation as: 

$$
\begin{equation}
x^\ast = g\alpha u^\ast
\end{equation}
$$

where $u^\ast$ is the expected number of photons hitting the pixel area, $\alpha$ is the quantum eﬃciency factor and $g$ is the analog gain. Now considering the system noise in each step of the pipeline in Fig. 1, we have:
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
\end{equation} \label{noise model}
$$

Note that both $k$ and $\delta^2$ are related to $g$, which is determined by the ISO setting of the camera.





## 3. The k-Sigma Transform

 Inspired by variance stabilizing transformations [[4](https://www.jstor.org/stable/2332343?origin=crossref&seq=1), [29](https://ieeexplore.ieee.org/document/5504216)], here we propose a k-Sigma Transform to avoid this problem. 

Speciﬁcally, we deﬁne a linear transform
$$
\begin{equation}
f(x) = \frac xk + \frac {\delta^2}{k^2}
\end{equation}
$$
According to our noise model of Eqn. $\eqref{noise model}$

$$
\begin{equation}
{f(x)\sim \mathcal P(\frac{x^\ast}{k})+\mathcal N(0, \delta^2)}
\end{equation} \label{transformed noise model}
$$

To analyze this distribution, a usual simpliﬁcation is to treat the Poisson distribution $\mathcal P(\lambda)$ as a Gaussian distribution of $N(\lambda,\lambda)$. Therefore:

$$
\begin{equation}
{
\begin{aligned}
& P\left(\frac{x^{*}}{k}\right)+\mathcal{N}\left(\frac{\sigma^{2}}{k^{2}}, \frac{\sigma^{2}}{k^{2}}\right) \\
\approx & \mathcal{N}\left(\frac{x^{*}}{k}, \frac{x^{*}}{k}\right)+\mathcal{N}\left(\frac{\sigma^{2}}{k^{2}}, \frac{\sigma^{2}}{k^{2}}\right) \\
=& \mathcal{N}\left(\frac{x^{*}}{k}+\frac{\sigma^{2}}{k^{2}}, \frac{x^{*}}{k} + \frac{\sigma^{2}}{k^{2}}\right) \\
=& \mathcal{N}\[f\left(x^{*}\right), f\left(x^{*}\right)]
\end{aligned}

}
\end{equation} \label{final noise model} 

 $$

Combining Eqn. $\eqref{transformed noise model}$ and Eqn. $\eqref{final noise model}$, the approximate distribution of $f(x)$ is: 

$$
\begin{equation}
f(x)=\mathcal{N}[ f\(x^{* }\right), f\left(x^{* } \]
\end{equation} 
\label{final noise model 1}
$$

Eqn. $\eqref{final noise model 1}$ indicates that the distribution of $f(x)$ only depends on $f(x^∗)$. As shown in Fig. 4, we can train a single network that takes$ f(x)$ as input and outputs $f(x^∗)$ as an estimation of $f(x^∗)$. The estimated true image value $ x^∗$ can then be computed by applying the inverted k-Sigma Transform $f^{−1}(\cdot)$ to $f(x^∗)$. ***In other words, we apply ISO-dependent transforms to the input and output of the neural network, so that the network can be trained using normalized data without considering the ISO setting.***



