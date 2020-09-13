python -c 'from keras.applications.vgg16 import VGG16; VGG16().summary()'

-gives error in Cmder


If you have keras in your environment

python -c "from keras.applications.vgg16 import VGG16; VGG16().summary()"




If you have tensorflow2:

python -c "from tensorflow.keras.applications.vgg16 import VGG16; VGG16().summary()"




python -c "from tensorflow.keras.applications.resnet50 import ResNet50; ResNet50().summary()"

Works on the anaconda prompt



I also use this to find versions and file locations:
python -c "import numpy;print (numpy.__version__);print (numpy.__file__)"