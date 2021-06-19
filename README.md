# Lane-Line-Detection
# Description

Lane detection is a critical component of self-driving cars and autonomous vehicles. It is one of the most important research topics for understanding driving scene. Lanes are identified using Computer Vision technique OpenCV, OpenCV-Python is a library of Python bindings designed to solve computer vision problems and Hough Line transformation. The project has two major sections, the first section is to develop an algorithm that will process each image and mark the lane lines on the road. The second section is to apply algorithm to a set of videos. 

##### STEP1 - Capturing and decoding Video file/Image: 
We will capture the video using VideoCapture object and after the capturing has been initialized every video frame is decoded (i.e. converting into a sequence of images).
##### STEP2 - Grayscale conversion of image: 
The video frames are in RGB format, RGB is converted to grayscale because processing a single channel image is faster than processing a three-channel colored image.
##### STEP3 - Reduce noise: 
Noise can create false edges, therefore before going further, it’s imperative to perform image smoothening. Gaussian filter is used to perform this process.
##### STEP4 - Canny Edge Detector: 
It computes gradient in all directions of our blurred image and traces the edges with large changes in intesity. Outlines strongest gardients in image. Based on the smoothed image, derivatives in both the x (width) and y (height) direction are computed; these in turn are used to compute the gradient magnitude of the image.
##### STEP5 - Region of Interest: 
This step is to take into account only the region covered by the road lane. A mask is created here, which is of the same dimension as our road image. Furthermore, bitwise AND operation is performed between each pixel of our canny image and this mask. It ultimately masks the canny image and shows the region of interest traced by the polygonal contour of the mask.
##### STEP6 - Hough Line Transform: 
The Hough Line Transform is a transform used to detect straight lines. The Probabilistic Hough Line Transform is used here, which gives output as the extremes of the detected lines
