# Practices and Applications of Convolutional Neural Network-Based Computer Vision Systems in Animal Farming: A Review

General review article of applications of convolution neural networks on animal farming. Notes that augmentation wise, a lot of papers seem to focus on rotating and flipping more than other augmentations.

Seems that frames per second is a matter of how much computation you have and on what timescale your object is moving around at. This is contrasted with resolution, where it seems to not always pay to have the highest resolution possible! Why might that be so?

Also, if you're recording a lot of data, it makes sense that you'll want to throw out the garbage frames that are similar to other ones. For that, the paper recommends algorithms like K-Means Clustering which can help reduce the amount of repetitive data you get from video. This may also help with class imbalance.

Color wise, generalizability may increase if you change from RGB to HSV or grayscale. You want to reduce the variance in the model from just the lighting conditions changing.

Interesting note: it seems like people may be *enhancing* images to make it easier for the model to learn? Is this because there isn't enough data, or why are they going out of their way to increase the ease of learning?

Rough rule of thumb is that you want about 5000 images/category.

Cool that some people do physical data augmentation in adding light to the scene in different ways to get differing conditions. Being able to augment conditions before the image/video is going to be the most effective as you're creating more realistic scenarios. Of note is that sometimes the tasks you're trying to accomplish are extremely sensitive, so data augmentation can severely hurt performance and make it ~impossible to learn.
