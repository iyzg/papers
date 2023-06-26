# CLIPPO: Image-and-Language Understanding from Pixels Only

Rather than two different transformers like CLIP, CLIPPO treats text as alt-text and only reads in images. There's some next sentence contrastive learning, but besides that, there are *no* word level losses.

It's cool that since they treat words as *coming through vision* than it is better able to deal with multilingual input. What's interesting is the amount of self-supervised learning losses they have like next sentence prediction and trying to embed sentences in different languages in the same space.

Good point on how good word tokenizers should shorten sequences, but because it is all images then it isn't able to do that. Really, I'm not sure what the future extensions for this work might be, like why do we want to do this? It does reduce parameters and complexity by only needing one model I suppose, but I don't know if I believe in this approach.

If there was some sort of unsupervised learner on top of it perhaps that was able to learn "tokenizations" that might be useful, but I'm not sure how that would work.

Not in this work in particular, but it is interesting that CLIP style models tend to embed in distinct areas rather than overlapping.

> Q: What's a scalable tokenizer-free way to generate text?
