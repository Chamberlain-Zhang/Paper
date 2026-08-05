# Learning Tone Curves for Local Image Enhancement
*(Digital Object Identifier 10.1109/ACCESS.2022.3178745)*

## ABSTRACT
> This papar propose a local tone mapping network (LTMNet) that learns a grid of tone curves to locally enhance an image.

![Overview of local image enhancement pipeline](./Figure-2.png)

## LTMNET
> - LTMNet layers serve two purpose: feature extraction and tone curve prediction. For feature extraction, a wide range of architecture can be used, as long as the reciptive fields of the output neurons composing the tone curve cover the image patches on which they are applied.   
> - Interpolation:  The tone curve interpolation module interp and transform all non-center pixels by a combination of neighbouring tone curve whose patch centers are closest to it.    
> - Tone Curve Constrains:  
>> 1. The entries in the lookup table are enforced to be non-decreasing to maintain intensity rank consistency.
>> 2. Maximum intensity is kept unchanged in the LUT to preserve information in the overposed regions.  
>> ![Tone Curve Constrain](./Figure-3.png "The tone curve constrains are implemented through intergrating and normalizing non-negative output neurons")

## DATASETS
> 1. **MIT-Adobe FiveK** contains 5,000 pairs of input and enhanced images retouched by five professional experts. However, this dataset involves mostly global tone mapping among other photo retouching operations[^1].
> 2. **HDR+** consist of 3.640 image bursts, which make up 28,461 images in total. Each burst is processed into a merged, aligned, and enhanced single output high dynamic range (HDR) image[^2].

## Metrics
> 1. **NIMA** can be used to automatically select the CLAHE parameters that give the most visually pleasing version of an enhanced image. NIMA is able to select images whithout halo artifacts[^3].

## References
[^1]:V. Bychkovsky, S. Paris, E. Chan, and F. Durand, ‘‘Learning photographic global tonal adjustment with a database of input/output image pairs,’’ in Proc. CVPR, Jun. 2011, pp. 97–104.
[^2]:S. W. Hasinoff, D. Sharlet, R. Geiss, A. Adams, J. T. Barron, F. Kainz, J. Chen, and M. Levoy, ‘‘Burst photography for high dynamic range and low-light imaging on mobile cameras,’’ ACM Trans. Graph., vol. 35, no. 6, pp. 1–12, Nov. 2016.
[^3]:H. Talebi and P. Milanfar, ‘‘NIMA: Neural image assessment,’’ IEEE Trans. Image Process., vol. 27, no. 8, pp. 3998–4011, Aug. 2018.
