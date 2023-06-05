# CocoNet: A deep neural network for mapping pixel coordinates to color values

The goal of the model is to learn a neural network to map from $(x, y)$ to $[R, G, B]$ values. Of course, once you learn this function you should be able to interpolate between and do either compression or some sort of upscaling!

This kind of reminds me of the MixUp paper and how you generate samples in between for smooth interpolation.

One advantage is that this method of training a network on just one image is that you don't need a massive dataset. That being said, I feel like this advantage is largely negated by the large models that most people are able to access now.

Not surprisngly, since this is only trained on one image, it has trouble in-painting with no texture knowledge. Interesting idea to map from coordinates to colors, but I'm not exactly sure the practical import of this.

> Q: Why is it that providing the model with three representations of the *same* coordinate would improve performance?