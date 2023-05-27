# Development and evaluation of a method to detect broilers continuously walking around feeder as an indication of restricted feeding behaviors

How they analyze behaviors is they take video, pass it into a neural network to generate bounding boxes, then use the geometric features in a SVM to classify behavior.

> Q: Why do they use a SVM to classify behavior and what geometric features are they taking from the bounding boxes? Would it not be more useful to instead use pose estimation?

The geometric features were the angle to the feeder, distance moved (measured by the centroid of the broiler's position), etc. They then used the SVM to differentiate between birds that were walking and all other birds based on the data.

Interesting that less chickens eating triggered the restricted eating behavior. It's when the situation is *more nebulous* that there is more competition, not when things are fully saturated. I feel like this sort of concept is expandable to more than just broilers around a feeding pen.
