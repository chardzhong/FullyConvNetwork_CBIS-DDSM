# Fully Convolutional Network Image Classification on the CBIS-DDSM dataset

This was my group's final project for our intro to ML class which I have tinkered with to try to get better performance. Our model was made to address an issue in traditional image classification using convolutional neural nets (CNNs): requiring uniform image sizes for both training and testing datasets. For datasets such as the Curated Breast Imaging Subset of Digital Database for Screening Mammography (CBIS-DDSM), which contains 2,620 scanned film mammography studies of varying dimensions, image resizing and, consequentially, information loss becomes a problem for traditional CNNs.

However, we can circumvent this image size requirement while also enjoying the qualities of fully connected 'dense' layers in CNNs by using a fully convolutional network (FCN). An FCN simulates the dense layers of a CNN using 1x1 convolutions allowing the model to accept varying image sizes as the absence of dense layers removes the size requirement.


## Performance
The model was able to demonstrate improved loss over training, achieving the highest testing accuracy of 67%. However, further hyperparameter testing could help improve testing accuracy and overfitting on training data.