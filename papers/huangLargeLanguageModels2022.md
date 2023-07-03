# Large Language Models Can Self-Improve

General method is that they use an LLM to generate CoT reasoning on unlabelled data that it is confident in which a new LLM is able to train on and perform better with. How is this consistent with the idea that synthetic data isn't good enough to train on? Maybe it's some sort of ShortStories kind of situation where training on just sequences isn't enough?

Really neat experiments where they generate artificial training examples and show that the model is still able to improve with CoT. They also try and distill the knowledge to smaller NN and find that between tiers (8, 62, 540)b, the model one tier down is able to outperform the untuned model one tier up. If anything, I would've loved to see this recursively continued. If the small model can learn the essentials, can it then teach the large model and improve it again?

For the bit about recursive forgetting, these might be self consistent. In the paper, they note that the temperature after doing this self finetuning goes up from $T = 0.7$ to $T = 1.2$ and postulate that this is because of the reduced entropy.

> Note: This entire premise of generating a bunch of CoT paths and training on the ones which are consistent relies on the fact that CoT paths show a relationship between accuracy and confidence. Luckily, that does seem to be the case from the author's experiments.

They also note that there might be another gap between greedy and diverse decoding.