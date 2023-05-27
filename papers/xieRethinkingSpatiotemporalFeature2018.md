# Rethinking Spatiotemporal Feature Learning: Speed-Accuracy Trade-offs in Video Classification

How does 3D convolutions work? Do you need them in all the layers or can you replace some with 2D convolutions for a more efficient netework? 

The authors find that top-heavy (3D convolutions in the later layers after 2D) performs better which is surprising because this *ignores low level motion cues*. They also make an architectural improvement in replacing the plain 3D convolutions with convolutions first across spatial dimensions before convolving through time.

> Q: Why do models all do this thing where they take a 256x256 image (which is power of 2), then crop it into 224x224. Is this like a standard? Aren't matrix multiplications more efficient when you make them powers of 2? If so, then why do people do this? I know that cropping might help stabilize training and is a form of regulation, but I don't understand why they do this sort of crop.

> "For fixed computation budget, Top-Heavy-I3D is often significantly more accurate than Bottom-Heavy-I3D. This suggests that 3D convolutions are more capable and useful to model temporal patterns amongst high level features that are rich in semantics."

I suppose this makes a little sense that 3D convolutions are better at extracting semantic information, **but** this does contradict the literature as the authors mention.

The authors have a cool graph where they show how because the weighting is so large for t=0 in the lower levels, 3D convolution is *ignoring* other timesteps, so it is basically equivalent to 2D. Why would that be though? Wouldn't it be beneficial to model action changes through time? Neat idea though to model network weights to demonstrate the effectiveness of an intervention.

> Q: Why is it that changing the filters to be spatial then temporal would reduce overfitting? I suppose this reduces expresiveness in forcing the model to learn the relationships separately, but the increase in performance is surprising. Might this problem be ameliorated with stronger regularization, or is there some prior baked into this that helsp the model?

> "As such, when I3D inflates the convolutions to 3D, only some of the features contain temporal information. However, by using separable temporal convolution, we can add temporal information to all 4 branches. This improves the performance from 78.4% to 78.9% on Mini-Kinetics-200."

Interesting that *adding* temporal dimensions to the Inception branches improves performance, but they focus instead on seeing how many 3D convolutions they can remove.

Note that the separable model beats out both the top-heavy and bottom-heavy models. It's just that those models are more *computationally friendly*.
