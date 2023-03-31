# Semantic Segmentation: MXNet algorthimic comparison on Sagemaker


Computer vision models have exploded in recent years. From Google’s self-driving cars and Tesla’s autopilot mode to Amazon’s Virtual Mirror, computer vision has transformed the face of modern technology. But machine learning image processing isn’t as easy as it may seem.

Training and validating computer vision and machine learning algorithms as well as image processing techniques require massive amounts of annotated data and high quality image annotation tool. That’s where image and video segmentation comes in.

Segmentation allows us to organize the data contained within images and videos into meaningful categories. Image classification and object detection may tell us the presence and location of certain objects. Segmentation allows us to dive deeper even in a real time. This type of segmentation involves grouping each pixel under a particular label. For example, any pixel belonging to a dog would be assigned under the same “dog” category.

This notebook proposes Semantic Segmentation solutions to check how well the MXNet algorithms FCN, PSP, Deeplab perform on same data. The unit of comparison is mIoU.

## About Data

### Using OXFORD-IIIT PET Dataset
----------------------------------------------
Credits: Omkar M Parkhi, Andrea Vedaldi, Andrew Zisserman and C. V. Jawahar

urls = 'http://www.robots.ox.ac.uk/~vgg/data/pets/data/images.tar.gz',
        'http://www.robots.ox.ac.uk/~vgg/data/pets/data/annotations.tar.gz'

### Contents:
---------------
* trimaps/       - Trimap annotations for every image in the dataset
                       Pixel Annotations: 1: Foreground 2:Background 3: Not classified
          
* xmls/		      - Head bounding box annotations in PASCAL VOC Format

* list.txt	      - Combined list of all images in the dataset
                       Each entry in the file is of following nature:
                           Image CLASS-ID SPECIES BREED ID
                           ID: 1:37 Class ids
                           SPECIES: 1:Cat 2:Dog
                           BREED ID: 1-25:Cat 1:12:Dog
                       All images with 1st letter as captial are cat images while
                       images with small first letter are dog images.
                       
* trainval.txt	  - Files describing splits used in the paper. However, random splits are better.
* test.txt	       

## Note:
Running this notebook would incur cost of about `$16-20` if not under Sagemaker trial period, else it will cost around `$12-13` on trial period because of `ml.p3.2xlarge` instance for training and 3 endpoint instances (`ml.m5.xlarge` or `ml.m4.xlarge` is sufficient) for testing.

## License
This notebook is created by Abhishek Gautam and is licenced under MIT.