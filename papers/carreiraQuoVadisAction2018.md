# Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset

The main question this paper tries to answer is how can we take models trained on 2D images and keep their advantages for 3 dimensions?

Firstly, the obvious solution is to slap a LSTM on the top of it that outputs the action that's happening and have it take in inputs from previous states along with the embedding from a ConvNet. There's also the idea of having a **3D Convnet**, but this can only handle fixed time dimensions and is extremely parameterized.

The issue with this simple LSTM model is that it's operating on only the highest level changes in the video, so solutions to that included optical flow that would go into a pretrained ConvNet and then put into a 3D model.

The authors take a separate approach by inflating 2D models into 3D through turning NxN weights into NxNxN. They only change some of the pooling layers into temporal layers since that doesn't need to be across time (time isn't symmetric), and they keep the flow networks. Although they aren't completely sure why it's helpful, they hypothesize that the flow computations introduce a form of soft recurrence into the model.

The authors find that pretraining does improve performance for video models and that denser models that have less of an image prior seem to be suited to take advantage of that video pretraining.
