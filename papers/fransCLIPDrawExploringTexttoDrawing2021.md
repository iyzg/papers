# CLIPDraw: Exploring Text-to-Drawing Synthesis through Language-Image Encoders

Creates images by aligning vector curves with CLIP embeddings. This method is supposed to produce more "natural" images than pixel optimization because it works on lines rather than individual pixels.

This work was one of the first to use a *differentiable renderer* which allows for vector graphics to optimized by things like gradient descent. They chose to use augmentations because without it, it is easy to find adversarial solutions which don't actually generate interesting images. Common thread that by *making the problem space more complex*, they force algorithms to generalize more. They note that without augmentation, it satisfies the loss without generating recognizable images.

Future works might want to introduce more constraints like that you not only have to have a high CLIP score, but also be able to fool a discriminator. It is also difficult to control how the drawing comes out, and it would be interesting to have some sort of conditioning such that you're able to place objects in parts of the canvas.