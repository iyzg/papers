# The Curse of Recursion: Training on Generated Data Makes Models Forget

Training on **model created** data is detrimental to training models, note that this is not *synthetic data* which some people have found is a decent substitute for normal human data. Although this is kind of at conflict with the recent paper where they trained on Midjourney images and got improved results. (I've yet to read that paper, so perhaps these two aren't in conflict)

The reason why *model collapse* happens is that each time you try and model a distribution, you start losing the tails more and more. This only gets worse as you continue training a model on more generated inputs which are themselves simulated distributions.

Two different types of model collapse: *early* and *late*. Early is when you lose the tails, late is when your mean shifts over time. You're also able to have different errors. There's statistical error (you'll never perfectly model a distribution) even with near infinite samples, and there's also functional approximation error where your model is unable to model the distribution. Their example is trying to fit a mixture of two Gaussian distributions with a single one which isn't fully possible.

> Note: They mix how much data each prior generation contibutes with $p_{i+1}=\alpha_i p_{\theta_{i+1}}+\beta_i p_i+\gamma_i p_0$

They first show that even with a perfect function fit, you still suffer from statistical error in that you lose the tails until you finally arrive at a single delta function (a singular point at the mean of the distribution).

There's some math in here that the sampling variance is equivalent to a random Gaussian walk, but I need to go back through the paper to understand what exactly is happening.