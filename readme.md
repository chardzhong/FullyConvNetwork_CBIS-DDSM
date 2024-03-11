# Fully Convolutional Network Image Classification on the CBIS-DDSM dataset

This repository contains the exported Google Colab notebook of our model. Inspired by the story of BakeryScan, a model designed to identify pastry types to expedite the checkout process in bakeries which was found to have incredible transferability to the seemingly unrelated task of classifying cancerous cells under a microscope ([article](https://towardsdatascience.com/bakeryscan-and-cyto-aiscan-52475b3cb779)), we set out to see if we could build a classification model on a known dataset of cancer imaging. Working with the Curated Breast Imaging Subset of Digital Database for Screening Mammography (CBIS-DDSM), which contains 2,620 scanned film mammography studies of varying dimensions, we aimed to build a CNN that could accept inputs without fixed dimensions and settled on using a fully convolutional model for its inherent ability to operate on inputs of any size. While our model was technically able to accept heterogeneous input dimensions, it showed clear issues of overfitting to the training data.
![Untitled](https://github.com/chardzhong/FullyConvNetwork_CBIS-DDSM/assets/44122104/2fb8a17d-2f22-4dd0-a6c1-49665215c7c8)

## A Revisit
Since then, I have been trying to better understand the field of FCNs to produce a better performing model. Unlike traditional CNNs which classify examples at the whole picture level, FCNs make predictions at every pixel and have been demonstrated to perform well in the task of semantic segmentation (Long et al., 2014). Naturally, this makes it well suited to the task of classifying mammograms, where we hope the model is able to identify specific patches of cancerous cells within the image. Even more so, FCNs (with the use of pooling operations) are translation invariant and equivariant, and can identify patterns regardless of their spatial coordinates.

Shen et al., (2019) also use the CBIS-DDSM dataset and a FCN to perform whole image classification. Patch classifiers were first trained on ROI annotations provided with each sample of the dataset and then used as high level filters in the top convolutional layers of the whole image model. 

...

Long, J., Shelhamer, E., & Darrell, T. (2014, November 14). Fully Convolutional Networks for Semantic Segmentation. arXiv.org. https://arxiv.org/abs/1411.4038v2

Shen, L., Margolies, L. R., Rothstein, J. H., Fluder, E., McBride, R., & Sieh, W. (2019, August 29). Deep Learning to Improve Breast Cancer Detection on Screening Mammography - Scientific Reports. Nature. https://doi.org/10.1038/s41598-019-48995-4

