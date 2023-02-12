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

### Camera calibration with the Zhang's algorithm
> Implemented camera calibration with the Zhang's algorithm based on 40 images of the checkerboard.
> - Extracted edges using the Canny Edege detector. 
> - Fitted straight lines to the edges with the Hough transform. 
> - Obtained the corner of the checkerboard from the intersection of the lines and label them.
> - Applued the Zhang's algorithm to get the intrinsic camera matrix ($K$) and external cammera calibration matrices. 
> - Measured the reprojection error for each point with the Euclidean Distance.

### Projective Stereo Reconstruction and Dense Stereo Matching
> Created a 3D reconstruction from a pair of images and applied Dense Stereo Matching for two rectified images.
> - Implemented image rectification by calculating the fundamental matrix, projection matrix and the homography matrix.
> - Run the implementation program of Loop and Zhang algorithm for image rectification. 
> - Constructed a set of interest point correspondences between the two images with Canny edge detector and SSD.
> - Applied 3D projective reconstruction based on the correpondances.
> - Caculated the disparity maps for two rectified images using the Census transform. Achieved a accuracy of 0.76 compared to the ground truth.

### Face Recognition and Object Detection
> Implemented face recognition based on dimensionality reduction algorithms and built Cascaded Adaboost Classifier for object detection.
> - Computed the covariance matrix for the face images vectors. 
> - Obtained low-dimensional representation for the face images with PCA (Principal component analysis) and LDA (Linear Discriminant Analysis).
> - Built a NN (Nearest Neighbor) classification agorithm. Achieved a classification accuracy of 1.
> - Built a Cascaded Adaboost Classifier for object detection based on the Viola and Jones approach. The aim is to achieve the arbitrary low false positive rate.
