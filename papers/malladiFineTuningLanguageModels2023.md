# Fine-Tuning Language Models with Just Forward Passes

Contribution of the paper is that they're able to fine-tune a model *in-place* which takes as much memory as inference. They do this using a zeroth-order algorithm which can not only estimate gradients, but it is also able to finetune based on objectives which don't have a gradient!

Standard ZO-SGD (Zeroth-order stochastic gradient descent) uses two forward passes and the difference in loss to estimate gradients. In this paper, they perturb weights in-place from a normal distribution to estimate loss which means they don't have to use more memory than inference.

> In comparison to in-context learning (ICL), it makes sense to do RLHF or other forms of fine-tuning because every token you add on at inference time is increased cost. It's much cheaper and more efficient to instead bake it into the model rather than relying fully on context.

For traditional Simultaneous Perturbation Stochastic Approximation (SPSA), it takes two forward passes to approximate the loss. You can then also add a learning rate to get ZO-SGD. With both of these methods, you need *twice* the inference memory since it also has to store the $z$ you sampled from a normal distribution.

The difference between those and MeZO is that they have a seed $s$ which they use to continually seed the random number generator. By doing so, you can resample $z$ *without additional* memory cost. Of course, this has an added computational cost, but it is generally memory that is the issue when fine-tuning these large language models.

Interestingly, convergence *isn't* reliant on the number of model parameters!

> Why? Lot's of math that I don't really want to fully work through right now.

This paper kind of reminds me of that old paper from OpenAI where they're able to train models using these stochastic optimization models and trained RL models with stochastic pertubations. Perhaps, this is an area of fruitful research where there are still interesting ideas to be found. Perhaps the most important idea in all these gradient free methods is that you can now tune models to things that are **ineffable**. Human preferences, F1 scores, etc. For something like open-endedness research, it's important that you're able to tune without gradients, as there oftentimes aren't easily accessible gradients for tasks you want to do.

Because they're using stochastic methods and zeroth-order estimation, they note that MeZO takes a large number of steps to reach strong performance, but they also haven't combined it with memory-efficient methods yet.

