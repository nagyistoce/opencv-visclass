## Project Description ##
This library provides a flexible feature-based image classification/object recognition framework made to augment OpenCV.  It is effective at classifying objects into broad categories (as demonstrated by the terrain classification demo) as well as very unique objects.  Classification is performed using the Bag of Visual Words (BOVW) data structure with linear Support Vector Machines (SVMs).  SURF and SIFT features are supported and the color histogram-based classification is also included (primarily for comparison).  The framework allows a large degree of customization through XML setup files.  Users can easily create and classify large image databases.

## Project Demo ##
<a href='http://www.youtube.com/watch?feature=player_embedded&v=jm7caqbBTkg' target='_blank'><img src='http://img.youtube.com/vi/jm7caqbBTkg/0.jpg' width='425' height=344 /></a>

This demo uses the OpenCV-Visclass and OpenCV 2.2 for real-time visual classification.  The classifier was trained using a series of labeled images in five terrain classes.  The robot pauses every few steps, takes a snapshot of the ground, and classifies the terrain to select an optimal gait.  All recognition code used in this demo is available for download, but propriety interface code (including the Boston Dynamics LittleDog library) is not available.

## Dependencies ##
  * [OpenCV2.2](http://opencv.willowgarage.com/)
  * [TinyXML 2.6.0](http://www.sourceforge.net/projects/tinyxml)
  * [wxWidgets 2.8.11](http://www.wxwidgets.org/)
  * [OpenCV-HistLib 0.2](http://code.google.com/p/opencv-histlib/) (included in download)

## About ##
This library was developed at the [UCSB Robotics Lab](http://robotics.ece.ucsb.edu) by [Paul Filitchkin](http://www.paulsf.com/) in partial fulfillment of his master's degree (thesis available [here](http://code.google.com/p/opencv-visclass/downloads/detail?name=TerrainClassificationThesis.pdf)).