---
title: U-Net
tags:
    - Generative models
---


# U-Net

## Architecture
U-Net, introduced in 2015, boasts a symmetrical structure comprising two paths:
- **Contracting Path:** Captures contextual information.
- **Expanding Path:** Enables precise localization, especially at object or feature boundaries.

## Training and Performance
Trained on a limited image dataset, U-Net surpassed sliding window CNNs, excelling in tasks like medical image segmentation.

## Diverse Applications
Beyond typical CNN usage, U-Net shines in generative and diffusion models (e.g., SD Imagine, DALL-E), initially applied to medical image segmentation. Later, it adopted tasks such as:
- Image segmentation
- Generating segment masks
- Upscaling resolution
- Diffusion models(gaussian noise to newly generated images)
- Cascading diffusion for higher resolution( 3 unit in a row for higer resolution )


See all of above cases we are taking image as input to give image as output
## Main Logic
The connecting path copies features from the opposite encoder part, adding them to the decoder. This consolidates both semantic and spatial information for precise pixel-level segmentation.
- as decoder has semantic infomation (like this total area has bike )
- as endoer has more spacial features (like these are the pixels the bike is)
- by taking both into consideration we get pixel perfect segmentation

## Paper Link
[U-Net: Convolutional Networks for Biomedical Image Segmentation](https://link.springer.com/chapter/10.1007/978-3-319-24574-4_28)

