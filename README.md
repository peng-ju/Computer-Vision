# Computer Vision
This repository contains the course projects from [ECE661 Computer Vision](https://engineering.purdue.edu/kak/computervision/) taught by [Prof. Avinash Kak](https://engineering.purdue.edu/kak/). Instead of simply using OpenCV, we implemented the key ideas in computer vision with our own code. Below are my code for these projects.   

### Homography with four point
> Computed the homography between two images based on manually selected four pairs of interest points.
> Apply affine transformation to an image.

### Remove Perspective and Affine distortion
> Removed the image distortion with three different methods.
> - Method 1: directly calculate the homography with 'undistorted scene'.
> - Method 2: first remove projective distortion by a homography that brings vanishing lines to the line at infinity. Then, remove affine distortion by a homography that restores the angle between two orthogonal lines.
> - Method 3: Calculate the dual degenerate conic and find the homography that maps it back to $C^{*}_{\infty}$.

### Key point search and build correspondance
> - Implemented Haris Corner detection algorithm to detect interest points for a pair of images from the same scene.
> - Established correspondance between interest points with SSD and NCC.  
> - Interest point detection and correspondance searching with SURF and SIFT algorithm from OpenCV.

### Image Mosaicing
> Stitched together five overlapping views/images of the same scene.
> - Found corresponding interests points betweeen adjacent images with SURF algorithm from OpenCV.
> - Rejected outliers with RANSAC algorithm.
> - Estimated the homography and refine the homography with nonlinear least-squares approach (Levenberg-Marquardt algorithm). 
> - Used pairwise homography to project the five images to a common scene.

### Image Segmentation
> Applied image segmentation for four images.
> - Implemented image segmentation with the Otsu algorithm. Iteratively run the Otsu algorithm for parameter tuning. 
> - Applied texture-based image segmentation for the same image set. Take the mean value and variance of a pixel window as the texture descriptor.
> - Extracted the contour of the foreground based on the result of image segmentation. Applied dilation and erosion to optomize the result. 

### Weather image classification 
> Built a texture-based image classification pipeline to determine the weather condition for 1000 images.
> - Extracted texture descriptors with three difference methods: channel normalization (per-channel mean and variance), LBP (Local Binary Pattern) and Gram Matrix.
> - Implemented a SVM multi-class classifier based on the feature vectors.
> - Achieved an accuracy of 0.975 with the channel normalization based SVM multi-class classifier.

