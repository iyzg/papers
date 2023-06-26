# Learning non-maximum suppression

The central issue is that before this paper, non-maximal suprresion (NMS) was simply a post-processing step that was outside the optimization pipeline. Because of this, they note how it is odd that such a simple algorithm couldn't be automated away, or at least hadn't been.

> Reminder for later: NMS is when a model proposes bounding boxes and you want to *supress* the bounding boxes that are over the same object. (You don't want 20) boxes all on the same object

They note that an issue with how models are trained is that they **aren't punished** for having multiple bounding boxes per object. Instead, they're **rewarded** since slight perturbations should still produce fairly confident boxes about an object. Ex. If I showed you a picture of an apple then shifted it down 10 pixels, you should still be fairly confident that it is an apple.

To note, their model works *only on detections* which means that it takes in no image features. It isn't so much that image features are bad, but that they wanted to show it was possible to train a NMS replacement with just detections.

Biggest improvements were a model architecture that was specifically designed to deal with overlap (they use a Hungarian algorithm to pair detections then) and allow detections to "talk to one another". Basically a sort of attention where detections are able to talk to each other to collaborate on which ones are the most important.

> Q: Would something like attention perform better for areas like this? Have vision foundation models entirely replaced this sort of research?

For most classes, this was an improvement on NMS, although the authors note that NMS was surprisingly competitive given that it's a simple greedy algorithm.