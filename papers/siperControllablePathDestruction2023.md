# Controllable Path of Destruction

Primary contribution is taking the iterable path of destruction method and adding a form of control. By having conditional inputs, the hope is that you're able to direct the output to follow the guidelines you feed it.

To note, these conditional inputs are **not** hard values. Rather, they are relative (below, above, on target) which they not is a larger distribution and they postulate learning to generate based on whether you need to increase or decrease is easier than learning relation between numbers.

General bit that this makes the model more controllable, but since they give it full vision instead of a small neighborhood, this has a lot more duplicated and similar levels.

Perhaps something that is worth thinking about is how can you guide the path of destruction? Perhaps some active learning sort of paradigm where you take the most information dense pixel or block from a game? How would that work for something that isn't classification, like most of the empty floor tiles are really not "information", but I'm not sure how you quite measure that for creation. What if you linked it up with OMNI and had GPT evaluate how useful it was to break a block?