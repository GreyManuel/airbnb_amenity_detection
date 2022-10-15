## Author:
## Grey Manuel

# Replicating Airbnb's Amenity Detection with Detectron2

This repository contains all the code from a 42-day project to replicate Airbnb's amenity detection using [Detectron2]

![example of how amenities might be detected in an image](https://raw.githubusercontent.com/mrdbourke/airbnb-amenity-detection/master/custom_images/airbnb-amenity-detection-workflow-large.png)

Sample image taken from: https://www.airbnb.com/rooms/2151100

**What's amenity detection?**

Object detection but for common and useful household items someone looking for an Airbnb rental might want to know about. For example, does this home have a fireplace?

Original inspiration was drawn from the article [Amenity Detection and Beyond — New Frontiers of Computer Vision at Airbnb]

## What's in this repo?

* Notebooks with 00-10 are all the steps I took to train the full model, largely unchanged from when I originally wrote them.
* `preprocessing.py` contains the preprocessing functions for turning [Open Images images & labels](https://storage.googleapis.com/openimages/web/index.html) into [Detectron2 style](https://detectron2.readthedocs.io/tutorials/datasets.html).
* `downloadOI.py` is a slightly modified downloader script from [LearnOpenCV](https://www.learnopencv.com/fast-image-downloader-for-open-images-v4/) which downloads only certain classes of images from Open Images, example:

```
# Download only images from the Kitchen & dining room table class from Open Images validation set
!python3 downloadOI.py --dataset "validation" --classes "Kitchen & dining room table"
```
* `app` contains a Python script with a [Streamlit](https://www.streamlit.io) app built around the model, if you can see the live version, Streamlit is what I used to build it.
* `custom_images` contains a series of different images related to the project, including various rooms around my house to test the model.

