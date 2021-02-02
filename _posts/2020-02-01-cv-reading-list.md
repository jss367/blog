All the papers to read:


Deeper networks are doing better, but they run into problems, like the vanishing gradient problem:
he vanishing gradient
problem (Zagoruyko & Komodakis, 2016

to solve that we have
 skip connections (He et al., 2016
 )
and batch normalization (Ioffe & Szegedy, 2015




Broad overview of deep learning:

Deep Learning Book (Bengio & Goodfellow)
Stanford's CS231n course notes: (not a paper per se, but super useful to read through. goes over the most recent advances in deep learning based CV)
"Practical Recommendations ..." paper from Bengio (a little bit outdated, but most of it holds up, many useful "tricks" of the trade)
Gradient descent techniques
The following is a list of papers that we frequently refer to / are closely related to things we've built (some are outdated at this point, but still good to know for historical context)

* The AlexNet paper
* The VGG paper
** Learn about how to go deeper through batch norm
* The Googlenet/Inception paper and the v4 follow up (skipping over v2 and v3)
** ResNet
[Deep Residual Learning for Image Recognition](https://arxiv.org/abs/1512.03385)

* Fully convolutional nets
* U-net paper
[U-Net: Convolutional Networks for Biomedical Image Segmentation](https://arxiv.org/abs/1505.04597) - 18 May 2015

Dilated convolutions

The ResNet paper and ResNet analysis paper
"How transferable are features in deep neural networks?" (empirical studies of fine-tuning)

The dropout paper
The FaceNet paper (triplet loss / learning an embedding)
Faster-RCNN (region proposal + detection with pure CNNs)
SSD paper and talk
Google's paper comparing different object detection methods
DeepMask (instance segmentation)
Batch normalization
[YOLO paper: You only look once: Unified, real-time object detection](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Redmon_You_Only_Look_CVPR_2016_paper.pdf) (2016), J. Redmon et al
There were improvements to it. Specifically, YOLOv3 is worth reading:
[YOLOv3: An Incremental Improvement](https://pjreddie.com/media/files/papers/YOLOv3.pdf)
Spatial pyramid pooling in deep convolutional networks for visual recognition (2014), K. He et al.
ML systems/infra papers/blog posts:

Google's TFX
Google's ML technical debt paper
Uber's ML infra
Facebook's ML infra
CV at pinterest
The classics (not directly relevant, but still worth reading, again for historical context):

The classics:

The Viola-Jones papers
[Rapid Object Detection using a Boosted Cascade of Simple Features](https://www.cs.cmu.edu/~efros/courses/LBMV07/Papers/viola-cvpr-01.pdf)

The HOG paper
The DPM (deformable parts model) paper
Papers specifically on computer vision for remote sensing:

Deep Learning in Remote Sensing: A Review (2017)
Towards Better Exploiting Convolutional Neural Networks for Remote Sensing Scene Classification (2016)
Not so essential, but still worth reading:

Unsupervised Visual Representation Learning by Context Prediction ( Self-supervised learning) (ICCV 2015)
End-to-End Instance Segmentation with Recurrent Attention (2017)

Other Computer Vision courses at Stanford with relevant materials:

CS331B: Representation Learning in Computer Vision: Research paper reading class, follow-up to CS231N. links to a good selection of CV papers
CS231A: Computer Vision, From 3D Reconstruction to Recognition
There is also a crowdsourced GitHub repo keeping track of the "top-100" papers in deep learning: https://github.com/terryum/awesome-deep-learning-papers
