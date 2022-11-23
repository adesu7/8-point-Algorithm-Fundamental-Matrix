# Fundamental Matrix calculation
Manual Implementation of 8 point algorithm to compute a Fundamental Matrix
a. Shifted and scaled the pixel coordinates
b. Compute the design matrix from sets of (at least) 8 points using SIFT keypoints
c. Performed an SVD of the design matrix to find its null space (you can use a
library function for the SVD)
d. Composed the draft fundamental matrix F
e. Performed an SVD of the draft fundamental matrix, set the smallest singular
value to zero and reassemble so that F now has determinant = 0
f. Calculated which correspondences are inliers and which are outliers using this
F. Accounted for some error because the keypoint coordinates won’t lie exactly on the epipolar line and took into account any
scaling you applied at step a.
g. Wrapped the steps b-f in a RANSAC loop that runs enough times to have a probability > 99% of finding 8 inliers and computing a good quality F.
h. Re-estimated F using all the inliers.
i. Compute F in terms of the original pixel coordinates (ie undo the effects of (step a).
