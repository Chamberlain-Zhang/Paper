# GAN: [Ways to improve GAN performance](https://towardsdatascience.com/gan-ways-to-improve-gan-performance-acf37f9f59b)

| [*Jonathan Hui*](https://jonathan-hui.medium.com/) |
| :------------------------------------------------: |
|                                                    |

**GAN models can suffer badly in the following areas comparing to other deep networks.**

- [**Non-convergence**](https://medium.com/@jonathan_hui/gan-why-it-is-so-hard-to-train-generative-advisory-networks-819a86b3750b#e633): the models do not converge and worse they become unstable.

- [**Mode collapse**](https://medium.com/@jonathan_hui/gan-why-it-is-so-hard-to-train-generative-advisory-networks-819a86b3750b#4987): the generator produces limited modes, and
- **Slow training:** the gradient to train the generator vanished.

As part of the GAN series, this article looks into ways on how to improve GAN. In particular,

- Change the cost function for a better optimization goal.
- Add additional penalties to the cost function to enforce constraints.
- Avoid overconfidence and overfitting.
- Better ways of optimizing the model.
- Add labels.

But be aware that this is a dynamic topic as research remains highly active.



## *Feature Matching*

The generator tries to find the best image to fool the discriminator. The “best” image keeps changing when both networks counteract their opponent. However, the optimization can turn too greedy and fall it into a never-ending cat-and-mouse game. This is one of the [scenarios](https://medium.com/@jonathan_hui/gan-why-it-is-so-hard-to-train-generative-advisory-networks-819a86b3750b#1d4a) that the model does not converge and mode collapses.

Feature matching changes the cost function for the generator to minimizing the statistical difference between the features of the real images and the generated images. Often, we measure the L2-distance between the means of their feature vectors. Therefore, feature matching expands the goal from beating the opponent to matching features in real images. Here is the new objective function:

