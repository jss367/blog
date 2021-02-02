How to train a neural network


* Do not jump into it. I know this is the opposite of most tutorials, where they just throw a ResNet50 at it, but that only works once someone has gone over the data and the model and everything is perfect. As in, that never works in "real" life. Once a dataset is clean and the pipeline is perfect, sure, it will work. Or if you are using a curated dataset, but I'm talking about real-world problems.

* Visualize everything possible - in the beginning, after augmentation, right before it goes into the network, what the weights and biases look like inside the network. Everything you can think to visualize, you should.


* Start at the shallow end
** we don't want to add a bunch of complexity at once- you will inevitably, but you'd like to limit it, don't try for a walk-off grand slam. swing the bat in the on-deck circle, test it, make sure you know it's swing


* have a baseline cnn that you use - set random seed- no data augmentation - i like to turn that on later - AFTER I OVERFIT

* train on a small subset - overfitthen train on a larger subset - overfit less


* Overfit and underfit
** You want to know where you dataset and model's limits are




* you should know what your first loss looks like. a sign of overfitting is when the loss drops significantly from the end of the first epoch to the beginning of the second


* when your model is small, you will underfit on it. increase the model capacity and watch the underfit go away

* as soon as you are able to scale, get a good metric. In general, the simple ones (f1 score, IOU, etc.) work just fine.

* especially if you're working with a lot of models (more common in industry than research), resnet50 is great.

