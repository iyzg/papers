# Artificial Artificial Artificial Intelligence: Crowd Workers Widely Use Large Language Models for Text Production Tasks

> Normally, a human makes a request to a computer, and the computer does the computation of the task. But artificial artificial intelligences like Mechanical Turk invert all that.  
> \- Jeff Bezos

The goal of the paper was to assess how many of the crowdsourced answers for text summarization were truly human and how many used synthetic LLM generated data. Whereas this data used to be 100% human, they were worried that it could no longer be trusted as a human level benchmark. The general finding is that 33-46% of the workers are using LLMs to write the abstracts.

Their general methodology is pretty simple of training an AI to discriminate between ChatGPT and real human responses which has an extremely high percentage rate. This seems to suggest that there is some sort of qualitative gap between what humans and AI are able to generate. Once you have a discriminative model, then you can just run that to determine how many of the MTurk workers are using AI tools. Something I wish they had validated is whether this would've worked if you switched to a different LLM. Do they have different flavors or do they all have some sort of recognizable fingerprint?

To further validate their findings, they also use keystroke tracking, but this feels pretty insignificant compared to the neural network.

Something interesting they do with their neural network is to have two different splits: one where they split training and test by the abstracts and one where they split normally. Even when the test split is entirely new abstracts, the model is still able to perform at ~97% accuracy which seems to suggest that there is something universal about what ChatGPT is generating.