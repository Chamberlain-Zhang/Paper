# Learning Tone Curves for Local Image Enhancement
*(Digital Object Identifier 10.1109/ACCESS.2022.3178745)*

## ABSTRACT
> This papar propose a local tone mapping network (LTMNet) that learns a grid of tone curves to locally enhance an image.

![Overview of local image enhancement pipeline](./Figure-2.png)

## LTMNET
> LTMNet layers serve two purpose: feature extraction and tone curve prediction. For feature extraction, a wide range of architecture can be used, as long as the reciptive fields of the output neurons composing the tone curve cover the image patches on which they are applied.  
> Interpolation:  The tone curve interpolation module interp and transform all non-center pixels by a combination of neighbouring tone curve whose patch centers are closest to it.  
> Tone Curve Constrains:
> 1. The entries in the lookup table are enforced to be non-decreasing to maintain intensity rank consistency.
> 2. Maximum intensity is kept unchanged in the LUT to preserve information in the overposed regions.
> ![Tone Curve Constrain](./Figure-3.png)
