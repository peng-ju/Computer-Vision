# Computer Vision
This repository contains the course projects from [ECE661 Computer Vision](https://engineering.purdue.edu/kak/computervision/) taught by [Prof. Avinash Kak](https://engineering.purdue.edu/kak/). Instead of simply using OpenCV, we implemented the key ideas in computer vision with our own code. Below are my code for these projects.   

### Homography_with_four_point
> Computed the homography between two images based on manually selected four pairs of interest points.
> Apply affine transformation to an image.

### Remove_Perspective_and_Affine_distortion
> Removed the image distortion with three different methods.
> - Method 1: directly calculate the homography with 'undistorted scene'.
> - Method 2: first remove projective distortion by a homography that brings vanishing lines to the line at infinity. Then, remove affine distortion by a homography that restores the angle between two orthogonal lines.
> - Method 3: Calculate the dual degenerate conic and find the homography that maps it back to $C^{*}_{\infty}$.

### Key_point_search_and_build_correspondance
> Implemented Haris Corner detection algorithm to detect interest points for a pair of images from the same scene.
> Built correspondance between interest points with SURF and SIFT.

### 


