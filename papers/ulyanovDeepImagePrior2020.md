# Deep Image Prior

The general idea from this paper is that the actual architecture provides information to solving a problem, it's *not just* about learning on a large set of data, but also about how well you design a model.

> Q: If this is true, then is it that by chasing benchmarks that we're actually getting closer to *understanding* how at least **artificial brains** learn and what kind of priors are useful for different environments? What sort of prior does attention bring?

> Q: Is it that we're learning true priors or are these also biased that we have? Further importance of datasets, because they inform model designs that might be inherently more biased.

What's really cool is that they show that *without* any training on a massive dataset, the architecture itself wants to head towards natural images. It has an easier time learning more "natural" images than training on noise, even though it is able to learn noise eventually at the limit.

> Q: Could you recover the classes that something like AlexNet trained on with just its weights or by seeing how quickly it adapts to certain classes?

It's also so cool that they're able to show how different models have stronger/weaker priors. Why is it that models with skip layers like a U-Net have weaker priors? Is it because these models are more expressive and require more data? Perhaps there's some direct inverse relationship between the two.

> Q: Is it true that more modern model architectures would have weaker priors since we have far more data?

Overall, this paper argues that architecture does matter, and deep learning is about more than just learning custom priors and about building stronger models whose priors line up with the world around us. Full paper has a lot of examples of how they use the prior to do denoising, inpainting, super-resolution, etc., but I think the general concept is already fruitful without elaborating on the exact different ways they use it.